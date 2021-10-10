# What?

This is my working repo to enable the user_u user type in SELinux under OpenSuSE Tumbleweed to run Plasma under Wayland.

# How?

```bash
git clone https://github.com/mihail-milev/tumbleweed-selinux.git
cd tumbleweed-selinux
checkmodule -M -m -o user_u_wayland_plasma.o user_u_wayland_plasma.te 
semodule_package -o user_u_wayland_plasma.pp -m user_u_wayland_plasma.o 
semodule -i user_u_wayland_plasma.pp 
```

# Why?

I love SELinux and I love distros, which support it. But in almost all distros the default configuration is to let normal users run as "unconfined_u". This is something I don't like. That's why I always define normal users to run as user_u. But when you do this, these users can't run anything in the GUI, because Wayland and (in my case) Plasma don't start. This is my repo, which contains the SELinux module sources to enable normal users to use GUI.

# License

MIT License, please consult LICENSE.md