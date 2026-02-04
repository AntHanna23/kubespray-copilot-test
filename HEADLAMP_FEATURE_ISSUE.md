# Enhancement Request: Add Headlamp as Kubernetes Web UI Option

## Issue Type
Enhancement / Feature Request

## Labels
- `kind/feature`
- `area/kubernetes-apps`
- `priority/medium`

## What would you like to be added

Add Headlamp as an optional Kubernetes web UI add-on to Kubespray deployments. Headlamp should be integrated similarly to how ArgoCD and other optional components are currently managed.

### Headlamp Overview
[Headlamp](https://github.com/headlamp-k8s/headlamp) is a modern, user-friendly Kubernetes web UI that provides:
- **WebSocket-based communication** for real-time updates and improved performance
- **Modern, intuitive interface** for viewing and managing Kubernetes clusters
- **Better performance** compared to traditional Kubernetes Dashboard
- **Plugin support** for extensibility
- **Multi-cluster support**
- **RBAC integration** for secure access control

### Proposed Implementation

The implementation should follow Kubespray's existing patterns for optional add-ons:

#### 1. New Ansible Role
Create a new role at `roles/kubernetes-apps/headlamp/` with:
- `defaults/main.yml` - Configuration variables (version, namespace, etc.)
- `tasks/main.yml` - Deployment tasks
- `templates/headlamp-namespace.yml.j2` - Namespace template

#### 2. Configuration Files
- Add `headlamp_enabled: false` to `inventory/sample/group_vars/k8s_cluster/addons.yml`
- Add Headlamp version and checksums to `roles/kubespray_defaults/vars/main/checksums.yml`
- Add download configuration to `roles/kubespray_defaults/defaults/main/download.yml`
- Add role dependency to `roles/kubernetes-apps/meta/main.yml`

#### 3. Default Configuration
```yaml
headlamp_enabled: false
headlamp_version: 0.39.0
headlamp_namespace: headlamp
```

#### 4. Deployment Source
Use official Headlamp Kubernetes manifests:
- URL: `https://raw.githubusercontent.com/headlamp-k8s/headlamp/v{version}/kubernetes-headlamp.yaml`

### Usage Example
```yaml
# Enable in inventory
headlamp_enabled: true
headlamp_namespace: headlamp  # optional, defaults to 'headlamp'
```

```bash
# Deploy with cluster
ansible-playbook -i inventory/mycluster/inventory.ini cluster.yml

# Or deploy standalone
ansible-playbook -i inventory/mycluster/inventory.ini cluster.yml --tags headlamp
```

## Why is this needed

### 1. Modern UI Experience
- Headlamp provides a more modern and responsive UI compared to the traditional Kubernetes Dashboard
- WebSocket-based architecture ensures real-time updates without polling, reducing server load
- Better user experience for cluster administrators and operators

### 2. Enhanced Performance
- Uses WebSockets instead of traditional HTTP polling
- Faster load times and more responsive interface
- Lower resource consumption on the cluster

### 3. Feature Parity
- Kubespray already supports multiple optional UIs and tools (ArgoCD, Kubernetes Dashboard via external means)
- Adding Headlamp gives users more choice based on their preferences and requirements
- Aligns with Kubespray's philosophy of being composable and flexible

### 4. Community Adoption
- Headlamp is gaining adoption in the Kubernetes community
- It's a CNCF sandbox project (as of knowledge cutoff)
- Well-maintained with active development

### 5. Ease of Integration
- Headlamp provides official Kubernetes manifests
- Integration follows existing Kubespray patterns (similar to ArgoCD)
- Minimal maintenance burden

## Additional Context

### Similar Integrations
This would be similar to existing integrations like:
- ArgoCD (`argocd_enabled`)
- Metrics Server (`metrics_server_enabled`)
- Cert Manager (`cert_manager_enabled`)

### Access Method
Once deployed, Headlamp can be accessed via:
- Port-forward: `kubectl port-forward -n headlamp svc/headlamp 8080:80`
- Ingress (if ingress controller is enabled)
- LoadBalancer service (in cloud environments)

### Documentation Updates Needed
- Update README.md to list Headlamp in supported components
- Add documentation in `docs/` directory (if applicable)
- Include usage examples in addon documentation

## Acceptance Criteria

- [ ] Headlamp role created with proper structure
- [ ] Configuration variables added to appropriate files
- [ ] Download configuration and checksums added
- [ ] Role integrated into kubernetes-apps meta dependencies
- [ ] Defaults set (disabled by default)
- [ ] Can be enabled via inventory configuration
- [ ] Deploys successfully on test cluster
- [ ] Accessible via configured service
- [ ] Documentation updated
- [ ] Follows Kubespray coding standards and patterns

## Implementation Notes

### Latest Version
- Current stable version: v0.39.0
- Manifest checksum (v0.39.0): `sha256:9a893b6ce1f14660f76c5d79848e64979944125406e762f76278143cd2b863a2`

### Default Deployment
By default, Headlamp will:
- Deploy to `headlamp` namespace
- Use `ghcr.io/headlamp-k8s/headlamp:latest` image (from official manifest)
- Create a Service on port 80 (internal)
- Require port-forwarding or ingress for external access

### Customization Options (Future)
Potential configuration options for future enhancements:
- Custom image registry/version
- Service type (ClusterIP, NodePort, LoadBalancer)
- Resource limits/requests
- Ingress configuration
- Authentication settings

## References

- [Headlamp GitHub Repository](https://github.com/headlamp-k8s/headlamp)
- [Headlamp Documentation](https://headlamp.dev/)
- [Official Kubernetes Manifest](https://github.com/headlamp-k8s/headlamp/blob/main/kubernetes-headlamp.yaml)
- [Kubespray Addons Documentation](https://github.com/kubernetes-sigs/kubespray/tree/master/docs)
