# Practice 1: GitHub Actions Basics

Create a workflow with **3 simple jobs** that demonstrate core concepts:

### Job 1: Say Hello (`hello-job`)

hello-job:
   runs-on: ubuntu-latest
    steps:
      - name: Simple greeting
        run: echo "Hello, GitHub Actions!"
      - name: Show current date
        run: date
      - name: List current directory
        run: ls -la

### Job 2: Check System (`system-job`)
   system-job:
      runs-on: ubuntu-latest
      steps:
      - name: Show system information
        run: |
          echo "=== System Info ==="
          echo "Operating System: $(uname -s)"
          echo "Current User: $(whoami)"
          echo "Working Directory: $(pwd)"
      - name: Create and display test file
        run: |
          echo "This is a test file" > test.txt
          cat test.txt


### Job 3: Summary Report (`summary-job`)
 summary-job:
    runs-on: ubuntu-latest
    needs: [hello-job, system-job]
    steps:
      - name: Wait message
        run: echo "Both previous jobs completed successfully!"
      - name: Final summary
        run: |
          echo "=== Workflow Summary ==="
          echo "Repository: ${{ github.repository }}"
          echo "Branch: ${{ github.ref_name }}"
          echo "Triggered by: ${{ github.actor }}"
          echo "All jobs completed at: $(date)"