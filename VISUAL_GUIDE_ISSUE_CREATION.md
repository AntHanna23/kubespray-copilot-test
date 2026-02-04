# Visual Guide: Creating the Headlamp GitHub Issue

This guide shows you what to expect when creating the issue on GitHub.

## Step-by-Step Visual Walkthrough

### 1. Navigate to Issues
```
GitHub Repo → Issues Tab → New Issue Button (Green)
```

### 2. Select Enhancement Template
You'll see something like:
```
┌─────────────────────────────────────────────────────┐
│  Enhancement Request                                 │
│  Suggest an enhancement to the Kubespray project    │
│                                    [Get started] ←   │
└─────────────────────────────────────────────────────┘
```

### 3. Fill in the Form

The form will have these fields:

```
┌──────────────────────────────────────────────────────────┐
│ Title: Add Headlamp as Kubernetes Web UI Option         │
├──────────────────────────────────────────────────────────┤
│                                                          │
│ What would you like to be added                         │
│ ┌────────────────────────────────────────────────────┐  │
│ │ [Copy content from HEADLAMP_FEATURE_ISSUE.md]      │  │
│ │                                                     │  │
│ │ Add Headlamp as an optional Kubernetes web UI...   │  │
│ └────────────────────────────────────────────────────┘  │
│                                                          │
│ Why is this needed                                      │
│ ┌────────────────────────────────────────────────────┐  │
│ │ [Copy the "Why is this needed" section]            │  │
│ │                                                     │  │
│ │ 1. Modern UI Experience...                         │  │
│ └────────────────────────────────────────────────────┘  │
│                                                          │
│                                   [Submit new issue]     │
└──────────────────────────────────────────────────────────┘

Right Sidebar:
├─ Labels: kind/feature ✓
├─ Projects: [Select your project board]
├─ Milestone: (optional)
└─ Assignees: (optional)
```

### 4. After Submitting

You'll see the created issue:
```
┌──────────────────────────────────────────────────────────┐
│ Add Headlamp as Kubernetes Web UI Option      #123 Open │
│                                                          │
│ @YourUsername opened this issue 1 minute ago            │
│                                                          │
│ Labels: kind/feature                                    │
│                                                          │
│ [Your issue content from the markdown file]             │
└──────────────────────────────────────────────────────────┘
```

### 5. Adding to Project Board

**Option A: From Issue Page**
```
Right Sidebar:
┌─────────────────────┐
│ Projects            │
│ ┌─────────────────┐ │
│ │ [Click here]   ↓│ │
│ └─────────────────┘ │
│                     │
│ Shows dropdown:     │
│ • Project 1         │
│ • Project 2    ←    │
│ • + New project     │
└─────────────────────┘
```

**Option B: From Project Board**
```
Project Board View:
┌───────────┬───────────┬───────────┬───────────┐
│ Backlog   │ To Do     │ In Prog.  │ Done      │
├───────────┼───────────┼───────────┼───────────┤
│ [+ Add]   │           │           │           │
│           │           │           │           │
│ Click '+' then search for your issue #123     │
└───────────┴───────────┴───────────┴───────────┘
```

### 6. Verify Issue on Board

You should see:
```
Project Board:
┌───────────────────────────────────────┐
│ 📋 Backlog                            │
├───────────────────────────────────────┤
│ ┌─────────────────────────────────┐  │
│ │ #123 Add Headlamp as K8s Web UI │  │
│ │ kind/feature                     │  │
│ └─────────────────────────────────┘  │
│                                       │
└───────────────────────────────────────┘
```

## Quick Copy-Paste Checklist

When creating the issue, copy these in order:

### ✅ Title
```
Add Headlamp as Kubernetes Web UI Option
```

### ✅ What would you like to be added
```
[Copy from line 8 to line 70 of HEADLAMP_FEATURE_ISSUE.md]
Starting with: "Add Headlamp as an optional Kubernetes..."
Ending with: "...ansible-playbook -i inventory/mycluster/inventory.ini cluster.yml --tags headlamp"
```

### ✅ Why is this needed
```
[Copy from line 72 to line 130 of HEADLAMP_FEATURE_ISSUE.md]
Starting with: "### 1. Modern UI Experience"
Ending with: "...Minimal maintenance burden"
```

### ✅ Additional Details (if using blank issue)
```
[You can also include the full content from HEADLAMP_FEATURE_ISSUE.md]
```

### ✅ Labels to Add
- `kind/feature` (required)
- `area/kubernetes-apps` (if available)
- `priority/medium` (if available)

### ✅ Project Board
- Select your project board from the dropdown
- Issue will be added automatically

## Success Criteria

✅ Issue created with unique number (e.g., #123)
✅ Issue has `kind/feature` label
✅ Issue appears on project board
✅ Issue content matches the template
✅ Issue is visible in the repository's issue list

## Common Issues and Solutions

### "I don't see the Enhancement template"
- Look for a link that says "Enhancement Request"
- If not available, click "Open a blank issue" and paste all content from HEADLAMP_FEATURE_ISSUE.md
- Add labels manually

### "I can't add labels"
- You may not have write permissions
- Ask a repository admin to add labels
- Or continue without labels (can be added later)

### "Project board dropdown is empty"
- Go to Projects tab first
- Create a new project board if needed
- Come back to the issue and add it to the board

### "I want to edit the issue after creation"
- Click the "..." menu on the issue
- Select "Edit"
- Make your changes
- Save

## Timeline Expectations

1. **Issue Creation**: ~5 minutes
2. **Adding to Board**: ~1 minute  
3. **Team Review**: Variable (hours to days)
4. **Approval**: Based on team process
5. **Implementation**: Once approved, ~1-2 days for development
6. **Testing**: ~1 day
7. **Merge**: After review and approval

---

**Good luck! 🚀**

The issue template is comprehensive and includes everything needed for the team to evaluate and implement the Headlamp feature.
