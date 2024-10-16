---
icon: send-backward
---

# Nohup: Running in the Background

When you want to keep your script running after you close your terminal or log out from the server, you can use `nohup`. This is especially useful for long-running processes, like a server, bot, or scheduled task. Here's how to do it step by step.

### **Basic Usage**

To run a Python script (or any) in the background using `nohup`, use this command:

```bash
nohup python3 main.py > output.log 2>&1 &
```

**Explanation:**

* `nohup`: Stands for "no hangup", it ensures the process won't terminate when the terminal is closed.
* `python3 main.py`: The script you want to run (replace `main.py` with your script).
* `> output.log`: Redirects the standard output (stdout) to a file called `output.log` (you can choose any filename).
* `2>&1`: Redirects the error output (stderr) to the same file (`output.log`).
* `&`: Runs the process in the background.

***

### **Checking if the Process is Running**

To verify that your script is running, you can check the process list:

```bash
ps aux | grep main.py
```

This command will list all processes that match `main.py` (replace `main.py` with your script's name). You should see an entry for your running Python script.

***

### **Stopping the Process**

If you need to stop the script later, first find its process ID (PID) with the `ps` command:

```bash
ps aux | grep main.py
```

Then, kill the process using `kill` followed by the PID:

```bash
kill <PID>
```

If the process doesn't stop with a regular `kill`, you can force it to stop using:

```bash
kill -9 <PID>
```
