# GitHub Actions Build Workflow

This repository is configured with GitHub Actions to automatically build and provide compiled JAR files.

## How It Works

The workflow automatically runs when:
- Code is pushed to `feat/folia-support`, `main`, or `master` branches
- A pull request is opened targeting these branches
- Manually triggered via the Actions tab

## Downloading Compiled Files

### Method 1: From Workflow Runs (Recommended)

1. Go to the [Actions tab](../../actions) in this repository
2. Click on "Build and Retrieve Compiled Files" workflow
3. Select a recent successful run (green checkmark ✓)
4. Scroll down to the "Artifacts" section at the bottom of the page
5. Download the artifacts:
   - **nightcore-shaded-jar**: Contains the main shaded JAR file
   - **nightcore-all-jars**: Contains all built JAR files from all modules

### Method 2: Manual Trigger

1. Go to the [Actions tab](../../actions)
2. Click on "Build and Retrieve Compiled Files" workflow
3. Click the "Run workflow" button
4. Select the branch you want to build
5. Click "Run workflow" to start the build
6. Wait for the build to complete
7. Download artifacts as described in Method 1

## Artifact Retention

Artifacts are kept for 30 days after the workflow run completes.

## What's Included

The workflow builds the entire Maven project and uploads:
- **Shaded JAR**: The main nightcore JAR with dependencies bundled
- **All JARs**: All module JARs including:
  - main
  - bridge
  - utils
  - spigot
  - paper

## Build Requirements

- Java 21
- Maven
- Dependencies are automatically downloaded from Maven repositories

## Troubleshooting

If the workflow fails:
1. Check the workflow logs in the Actions tab
2. Look for compilation errors or dependency issues
3. Ensure all required dependencies are accessible
4. Check that the Java version (21) is correctly configured

## For Developers

The workflow configuration is located at `.github/workflows/build-and-test.yml`.

To modify the workflow:
1. Edit the workflow file
2. Test changes by pushing to a branch or creating a pull request
3. Monitor the Actions tab for results
