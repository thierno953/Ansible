# Ansible Loops and Conditionals

## Loops

- Sometimes you want to repeat a task multiple times, in computer programming this is called as loops. Suppose you want to perform some repetitive task then one way would be duplicate tasks for multiple time something which can be quite tedious. Ansible loops are very effective to perform repetitive tasks with fewer lines of code.
- The loop keyword executes the same task multiple times. It stores the value of each item in a variable called item. So, instead of specifying the names of the users to be added, simple specify a variable called item enclosed between double curly braces as shown below.

```bash
name : "{{ item }}"
```

## Conditionals

- In Ansible, you can define conditions that will be evaluated before a task is executed. When a condition is not met, the task is then skipped. This is done with the when keyword, which accepts expressions that are typically based on a variable or a fact.
