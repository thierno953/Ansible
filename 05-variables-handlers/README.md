# Ansible Variable and Handlers

## Ansible Handlers

- Handlers are just like other tasks in a playbook, the difference being that they are triggered using the notify directive, and are not only run when there is a change of state.
- A handlers should have a globally unique name within the playbook.
- If multiple handlers are defined with the same name, only the first on will be called. The remaining handlers will be ignored.
- Handlers always run in the order in which they are defined in the handlers section, and not in the notify section.
- If the state of a task remains unchanged, the handler will not run. As such, handlers help in achieving idempotency. Hence a handler task only runs if there is a change in state, else it doesn't.
- To define a handler, the notify and handlers directives are used. The notify directive triggers the execution of the task(s) specified in the handlers section.
