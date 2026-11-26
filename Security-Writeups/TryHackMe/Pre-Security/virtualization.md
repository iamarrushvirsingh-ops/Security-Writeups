# Virtualization

## Virtualization

- Virtualization made it possible to use a single physical server for multiple services.
- A software layer called a **hypervisor** was introduced. It acts like a referee between the virtual machines, letting each one behave independently, like its own physical computer.

## Containers

- A **container** is a lightweight, isolated environment that runs a single application along with everything it needs to work.
- Containers behave like small, self-contained spaces because:
    - They package the application together with its dependencies (libraries, tools, versions).
    - They share the host's operating system, so they start almost instantly.
    - They stay isolated from each other, so one misbehaving container doesn't affect the others.
    - They run the same way on any machine, which makes them great for development, testing and scaling up.

- **Docker** is the most popular and easiest tool for running containers.
- Docker is an open-source platform that makes it simpler to build, deploy and run applications using containers.

## Types of Hypervisor

Hypervisors come in two main types, each used for different situations, from home labs to large data centres:

- **Type 1** hypervisors run directly on the physical hardware. This makes them fast and efficient, ideal for servers and professional environments.
- **Type 2** hypervisors run on top of an existing operating system (like VirtualBox on Windows or Linux). This makes them easier to install, ideal for learning, testing or small setups.

## Key Terms

- **Virtualization**: Lets one physical computer act like multiple separate computers.
- **Hypervisor**: The "manager" software that creates and runs the virtual computers.
- **Lab Machine (VM)**: A whole virtual computer inside the real one, with its own operating system.
- **Container**: A small, isolated box for one app that shares the host's operating system.
- **Container Image**: A pre-packed template (recipe) used to create containers.
- **Network Ports**: Numbered entry points that apps use to talk over the network.
