 ## Progress Class

This code defines a `Progress` class that can be used to track the progress of a task and print a progress bar.

### How to use the `Progress` class

To use the `Progress` class, you first need to create an instance of the class. You can do this by calling the `Progress` constructor, which takes two arguments:

* `current`: The current progress of the task.
* `total`: The total number of steps in the task.

Once you have created an instance of the `Progress` class, you can use the `print_progress` method to print a progress bar. The `print_progress` method takes one argument:

* `current`: The current progress of the task.

The `print_progress` method will print a progress bar that shows the current progress of the task, as well as the percentage of the task that has been completed.

### Example

Here is an example of how to use the `Progress` class:

```python
import sys

# Create an instance of the Progress class
progress = Progress(0, 100)

# Print the progress bar
for i in range(100):
    progress.print_progress(i)
```

This code will print the following progress bar:

```
Progress: [========================================] 100% 100 of 100
```

### Code Explanation

The `Progress` class is defined as follows:

```python
class Progress:
    def __init__(self, current, total) -> None:
        self.current = current
        self.total = total
        pass

    def print_progress(self, current) -> None:
        self.current = current
        progress = current / self.total
        bar_length = 40
        progress_bar = (
            "["
            + "=" * int(bar_length * progress)
            + "-" * (bar_length - int(bar_length * progress))
            + "]"
        )
        sys.stdout.write(
            "\rProgress: [{:<40}] {:.2%} {} of {}".format(
                progress_bar, progress, current, self.total
            )
        )
        sys.stdout.flush()
```