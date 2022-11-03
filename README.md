# Intro to Ansible for Network Engineers
(30 minutes)


When getting started with network automation, Ansible is a super useful tool to learn. It will provide a helpful platform and framework for connecting to network devices in a secure way to make configuration changes, read operational data and build reports. You can run Ansible locally on your laptop and connect to a ton of devices to save time in your next change window, even if it is just grabbing “show” commands to put into a file and view the differences between the state before and after your change. Ansible was originally designed for compute and cloud engineers, so this session is focused on how to learn it from a network engineer’s perspective, assuming no previous knowledge.  


These demos are using the [NSO DevNet Sandbox](https://devnetsandbox.cisco.com/RM/Diagram/Index/43244b33-7af5-4e6b-9b48-58cadf3d2d24?diagramType=Topology), not because we are using NSO, but it has a nice topology (IOS, NXOS, ASA, XR) and we can reserve it for a week at a time.


The dockerfile provided follows [Barry Weiss' super helpful Ansible repo](https://github.com/barweiss45/Ansible-IOSXE-Always-On-Demo), check it out for more examples. This repo has a `requirements.txt` file for the version of Ansible used and a dockerfile. See Barry's repo on how to set it up, only basic instructions will be given here. If you do want to use docker, here are some commands that will get it up and running from my adaptation of Barry's repo.


```bash
git clone https://github.com/jabelk/intro-to-ansible-webinar.git
cd intro-to-ansible-webinar
docker build -t intro-ansible-webinar:latest .
docker run -dit --rm --name webinar-demo intro-ansible-webinar:latest
docker exec -it webinar-demo bash
cd intro-to-ansible-webinar/
cd demo-part-1/
ansible-playbook -i inventory.ini 0-playbook-basics.yaml -v
```

If you are using docker, you can attach [VS Code to it](https://code.visualstudio.com/docs/remote/attach-container). You don't need to use docker, you can set up a virtual environment, or install Ansible on your device directly. Installing Ansible is not within the scope of this tutorial.

Tips:

- shift tab
- vs code for yaml
- muscle memory
- comment out
- don't make too many changes at once
- double quotes outside everything
- single quotes within double quotes.
- gather facts no
- looks for templates in playbook directory, so don't need full path unless playbooks are in a dir
- Ansible documentation and examples
- ignore_errors for uncertain playbooks