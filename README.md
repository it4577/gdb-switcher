# gdbs : gdb-switcher

Just simple gdb switcher between peda, gef, pwndbg and radare2

- [cyrus-and/gdb-dashboard: Modular visual interface for GDB in Python](https://github.com/cyrus-and/gdb-dashboard)
- [hugsy/gef: Multi-Architecture GDB Enhanced Features for Exploiters & Reverse-Engineers](https://github.com/hugsy/gef)
- [longld/peda: PEDA - Python Exploit Development Assistance for GDB](https://github.com/longld/peda)
- [pwndbg/pwndbg: Exploit Development and Reverse Engineering with GDB Made Easy](https://github.com/pwndbg/pwndbg)
- [radare/radare2: unix-like reverse engineering framework and commandline tools](https://github.com/radare/radare2)


## Usage

https://asciinema.org/a/3xQ3Sh83JTcsdWOaG7ubMy66T
[![asciicast](https://asciinema.org/a/3xQ3Sh83JTcsdWOaG7ubMy66T.svg)](https://asciinema.org/a/3xQ3Sh83JTcsdWOaG7ubMy66T)

#### 1. Select debugger and launch.
```bash
$ gdbs executable

[*] Which debugger ?

1 : Legacy GDB
2 : gdb-dashboard
3 : gef
4 : peda
5 : pwndbg
6 : radare2

Select {1,2,3,4,5,6}

[+] gdb-switch => debugger
[+] debugger execution
Reading symbols from ./executable...done.

debugger$
```

#### 2. Just configure debugger and execute gdb later.

```bash
$ gdbs

[*] Which debugger ?

1 : Legacy GDB
2 : gdb-dashboard
3 : gef
4 : peda
5 : pwndbg
6 : radare2
3
[+] gdb-switch => peda

$ ❯ gdb -q ./executable
Reading symbols from ./executable...(no debugging symbols found)...done.
gdb-peda$ 
```


## Environment

Bash in Ubuntu

## Install

#### 1. Clone

Clone `gdb-switcher` repo.

```bash
$ git clone https://github.com/it4577/gdb-switcher.git
```

#### 2. (Optional) Install debugger

Install debugger only if those are not installed before.

```bash
$ ./install.sh
```

#### 3. Configuration

The script adds `gdbs()` function in `~/.bashrc`.
If you have your own configuration, add your config in `~/.gdbinit-my`.

```bash
$ ./setup.sh
```

## Uninstall

Just delete the added `function gdbs()` at the end of `~/.bashrc`.

#### 1. Check `~/.gdbinit`

#### 2. Remove `function gdbs()` in `~/.bashrc`.

```bash
# gdbs : gdb-switcher
function gdbs() {
      echo -e "\n[*] Which debugger ?"
...
}
```
