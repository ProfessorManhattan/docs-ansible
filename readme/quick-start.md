## One-Line Install Method

Looking to install {{ role_pretty_name }} without having to deal with [Ansible](https://www.ansible.com/)? Simply run the following command that correlates to your operating system:

**Linux/macOS:**

```shell
curl -sS https://install.doctor/{{ role_name }} | bash
```

**Windows:**

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://win.install.doctor/{{ role_name }}'))
```

And there you go. Installing {{ role_name }} can be as easy as that. If, however, you would like to incorporate this into an Ansible playbook (and customize settings) then please continue reading below.

**Important Note:** *Before running the commands above you should probably directly access the URL to make sure the code is legit. We already know it is safe but, before running any script on your computer, you should inspect it.*
