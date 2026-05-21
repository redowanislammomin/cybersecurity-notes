# Metasploit Cheat Sheet

**MSFconsole** 
>commonly used

show exploits          # list all exploits

show payloads          # list all payloads

show auxiliary         # list all auxiliary modules

search <name>          # search for a module

info                   # info about current module

use <name/number>      # load a module

show options           # show module options

show targets           # show supported platforms

show advanced          # show advanced options

check                  # check if target is vulnerable

**Setting Values**
>important to know 

set <option> <value>   # set a value (e.g. set LHOST 10.0.0.1)

setg <option> <value>  # set a value globally

set target <number>    # set target OS/platform

set payload <payload>  # set the payload

**Running Exploits** 
>first 2 commonly used

exploit                # run the exploit
	
exploit -j             # run in background

exploit -z             # run, don't interact with session

exploit -e <encoder>   # run with specific encoder

**Sessions** 
>c = commonly use

sessions -l            # list sessions [c]

sessions -l -v         # list sessions (verbose)

sessions -s <script>   # run script on all sessions

sessions -K            # kill all sessions [c]

sessions -c <cmd>      # run command on all sessions

sessions -u <id>       # upgrade shell to meterpreter[c]

**Meterpreter**  
>commonly used

help                   # show help

sysinfo                # system info

ls                     # list files

ps                     # list processes

migrate <pid>          # migrate to a process

shell                  # drop into a shell

background             # background the session

getsystem              # try to get SYSTEM access

getprivs               # get all privileges

hashdump               # dump password hashes
