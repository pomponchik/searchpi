# searchpi

This is a very stupid CLI tool that is designed to search for SSH-ready devices on your local network, starting with those with the most senior local IP addresses.

Before using this tool, install [`nmap`](https://nmap.org/) on your computer. Then install the tool by [`pip`](https://pip.pypa.io/en/stable/installation/):

```bash
pip install searchpi
```

And use:

```bash
searchpi 192.168.1.0/24 pomponchik ~/.ssh/id_rsa.pub
```

Here `192.168.1.0/24` means the range of addresses we are looking at, `pomponchik` is the username and `~/.ssh/id_rsa.pub` is the name of the SSH key file.

The command will print to the standard output the command that you will need to execute to connect to the remote machine via SSH:

```bash
>>> searchpi 192.168.1.0/24 pomponchik ~/.ssh/id_rsa.pub
ssh pomponchik@192.168.1.16
```

You can save your energy if you try to call the received command in the same line of code:

```bash
eval "$(searchpi 192.168.1.0/24 pomponchik ~/.ssh/id_rsa.pub)"
```
