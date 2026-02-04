# Instructions: Creating the Headlamp Feature Issue

## Overview
This document provides step-by-step instructions for creating a GitHub issue for the Headlamp feature request and adding it to the project board.

## Prerequisites
- GitHub account with access to the `AntHanna23/kubespray-copilot-test` repository
- Permissions to create issues and manage project boards

## Step 1: Create the GitHub Issue

### Option A: Using GitHub Web UI

1. **Navigate to the repository**
   - Go to: https://github.com/AntHanna23/kubespray-copilot-test

2. **Open the Issues tab**
   - Click on the "Issues" tab in the repository navigation

3. **Create a new issue**
   - Click the green "New issue" button

4. **Select the Enhancement template**
   - You should see issue templates. Click "Get started" next to "Enhancement Request"
   - If templates don't appear, you can manually select "Enhancement Request" or create a blank issue

5. **Fill in the issue details**
   
   **Title:**
   ```
   Add Headlamp as Kubernetes Web UI Option
   ```
   
   **For "What would you like to be added" section:**
   - Copy the content from the "What would you like to be added" section in `HEADLAMP_FEATURE_ISSUE.md`
   
   **For "Why is this needed" section:**
   - Copy the content from the "Why is this needed" section in `HEADLAMP_FEATURE_ISSUE.md`
   
   You can also copy the entire content from `HEADLAMP_FEATURE_ISSUE.md` if creating a blank issue.

6. **Add labels**
   - Click on "Labels" on the right sidebar
   - Add: `kind/feature`
   - If available, also add: `area/kubernetes-apps`, `priority/medium`

7. **Submit the issue**
   - Click "Submit new issue"
   - Note the issue number (e.g., #123)

### Option B: Using GitHub CLI (if available)

```bash
# Navigate to the repository directory
cd /path/to/kubespray-copilot-test

# Create the issue using the content from the markdown file
gh issue create \
  --title "Add Headlamp as Kubernetes Web UI Option" \
  --body-file HEADLAMP_FEATURE_ISSUE.md \
  --label "kind/feature"
```

## Step 2: Add Issue to Project Board

### Finding Your Project Board

1. **Navigate to Projects**
   - In the repository, click on "Projects" tab
   - OR go to: https://github.com/AntHanna23/kubespray-copilot-test/projects

2. **Identify the project board**
   - Look for an existing project board (e.g., "Kubespray Development", "Feature Roadmap", etc.)
   - If no project board exists, you may need to create one first

### Adding to Existing Project Board (Web UI)

**Method 1: From the Issue Page**

1. Open the newly created issue
2. Look for "Projects" in the right sidebar
3. Click on "Projects"
4. Select the project board from the dropdown
5. The issue will be added to the project (usually in a "To Do" or "Backlog" column)

**Method 2: From the Project Board**

1. Open the project board
2. Find the appropriate column (e.g., "To Do", "Backlog", "Feature Requests")
3. Click the "+" button or "Add cards" button in that column
4. Search for and select your issue
5. The issue will be added to that column

### Adding to Project Board (GitHub CLI)

```bash
# List available projects to get the project ID
gh project list --owner AntHanna23

# Add issue to project (replace PROJECT_ID and ISSUE_NUMBER)
gh project item-add PROJECT_ID --owner AntHanna23 --url https://github.com/AntHanna23/kubespray-copilot-test/issues/ISSUE_NUMBER
```

## Step 3: Creating a Project Board (if none exists)

If you need to create a new project board:

1. **Navigate to Projects tab**
   - Click "Projects" in the repository navigation
   - Click "New project"

2. **Choose template**
   - Select "Board" or "Table" template
   - Or start with a blank project

3. **Configure the board**
   - Name it (e.g., "Kubespray Feature Development")
   - Add description
   - Set visibility (Public or Private)

4. **Set up columns** (for Board view)
   - Common columns: "Backlog", "To Do", "In Progress", "Review", "Done"
   - Or: "📋 Backlog", "🔨 In Progress", "👀 Review", "✅ Done"

5. **Add the issue**
   - Follow the steps in "Adding to Existing Project Board" above

## Step 4: Verify

1. **Check the issue**
   - Navigate to the issue
   - Verify it has the correct labels
   - Verify it shows up in the "Projects" section

2. **Check the project board**
   - Navigate to the project board
   - Verify the issue card appears
   - Verify it's in the correct column

## Step 5: Next Steps

Once the issue is created and on the project board:

1. **Triage and prioritize**
   - Add priority labels if not already added
   - Move to appropriate column (Backlog, To Do, etc.)
   - Add milestone if applicable

2. **Discussion**
   - Team members can comment on the issue
   - Refine requirements
   - Assign to developer when ready

3. **Implementation**
   - When ready to implement, move to "In Progress"
   - Create a branch referencing the issue number
   - Submit PR linking to the issue

## Troubleshooting

### Cannot create issues
- Verify you have write access to the repository
- Check if issues are enabled in repository settings

### Cannot add to project board
- Verify the project board is linked to the repository
- Check permissions on the project board
- Ensure you're using the correct project board

### Labels don't exist
- You may need to create custom labels first
- Go to Issues → Labels → New label
- Create `kind/feature`, `area/kubernetes-apps`, etc.

## References

- [GitHub Issues Documentation](https://docs.github.com/en/issues)
- [GitHub Projects Documentation](https://docs.github.com/en/issues/planning-and-tracking-with-projects)
- [GitHub CLI Issue Commands](https://cli.github.com/manual/gh_issue)
- [GitHub CLI Project Commands](https://cli.github.com/manual/gh_project)
