# How to use

## Open /usr/bin/start_server
    Edit to your settings > 
                    locale(line 3)
                    n_jar(line 13)
                    ram(line 14)
                    a_scr(line 18)

## To turn on the server automatically after restarting the server(VPS/VDS) you must do move files
    /usr/lib/systemd/system/start_server.service
    CONSOLE > 
        chmod -R 777 /usr/lib/systemd/system/start_server.service
        ln -s /usr/lib/systemd/system/start_server.service /etc/systemd/system/multi-user.target.wants/start_server.service
        chmod -R 777 /usr/bin/start_server
        systemctl enable start_server
## How to automatically run server?
    options > start | stop | reload
    You have a two options:
        systemctl <OPTIONS> start_server
        service start_server <OPTIONS>
    To check if the server is active, type the command:
        systemctl status start_server
    
    This is what a properly turned on server looks like
        https://imgur.com/a/VVgxEF1

## Arguments to boot the server
    You must shut down the server to use these arguments...
    How to use? Use this method - start_server --"type a argument"

    Argument:
        --b     <- daily backups
        --dl    <- logs deleted every 3 days
        --db    <- backup deleted every 7 days
        --c     <- checking if the server is on