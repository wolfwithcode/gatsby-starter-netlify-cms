---
templateKey: blog-post
title: Setting up a Bitbucket pipeline to run a script on a Virtual Private
  Server (VPS)
date: 2023-12-02T11:52:08.494Z
description: Setting up a Bitbucket pipeline to run a script on a Virtual
  Private Server (VPS) when a pull request (PR) is merged into a branch involves
  several steps.
featuredpost: true
featuredimage: /img/chemex.jpg
---
Setting up a Bitbucket pipeline to run a script on a Virtual Private Server (VPS) when a pull request (PR) is merged into a branch involves several steps. Here's a general outline of the process:

1. **Prepare Your VPS**:

   * Ensure your VPS is accessible via SSH.
   * Install any necessary software on the VPS that the script requires.
   * Place your script on the VPS in a known location.
2. **Set Up SSH Key for Bitbucket Pipeline**:

   * Generate an SSH key pair specifically for Bitbucket to use.
   * Add the public key to the `~/.ssh/authorized_keys` file on your VPS.
   * Add the private key to your Bitbucket repository's settings under "Pipelines" -> "SSH Keys".
3. **Configure Bitbucket Pipelines**:

   * Enable Pipelines in your Bitbucket repository.
   * Create a `bitbucket-pipelines.yml` file in the root of your repository.
   * Define a pipeline that triggers on a merge into your specific branch.
4. **Script Execution Pipeline**:

   * In the `bitbucket-pipelines.yml` file, define the steps to SSH into your VPS and execute the script.
   * You can use an SSH pipe in Bitbucket Pipelines for this purpose.
   * Ensure your pipeline script handles any necessary environment variables or parameters.
5. **Handle Merge Trigger**:

   * Configure the pipeline to trigger when a PR is merged. You can do this by specifying the branch name in the `branches` section of your `bitbucket-pipelines.yml`.
6. **Testing and Security**:

   * Test your pipeline with a dummy PR to ensure it works as expected.
   * Ensure that the SSH keys are secure and the script on your VPS does not pose any security risks.

Here's a basic example of what your `bitbucket-pipelines.yml` might look like:

```yaml

```

Replace `your-branch-name`, `your_vps_username`, `your_vps_ip`, and `/path/to/your/script.sh` with your specific details.

Remember, this is a basic guide. Depending on your exact requirements and setup, you might need to adjust or expand on these steps. Always consider best practices for security and maintainability.