# How to use

## Open /usr/bin/start_server
    Edit to your settings > 
                    locale(line 3)
                    n_jar(line 13)
                    ram(line 14)
                    a_scr(line 18)

## Enable CRONTAB (crontab -e) enter at the end:
    ### https://crontab.guru/ 
    0  3 *   * *	start_server --b     <backup every day at 3 am>
    10 3 */3 * *    start_server --dl    <log deletion every 3 days at 3:10 am>
    20 3 */7 * *    start_server --db    <backup deletion every 7 days at 3:20 am>

## To turn on the server automatically after restarting the server(VPS/VDS) you must do move files
    /usr/lib/systemd/system/start_server.service
    CONSOLE > 
        chmod -R 777 /usr/lib/systemd/system/start_server.service
        ln -s /usr/lib/systemd/system/start_server.service /etc/systemd/system/multi-user.target.wants/start_server.service
        chmod -R 777 /usr/bin/start_server
        systemctl enable start_server
## How to automatically run server?
    OPTIONS > start | stop | reload
    You have a two options:
        systemctl <OPTIONS> start_server
        service start_server <OPTIONS>
    To check if the server is active, type the command:
        systemctl status start_server
    
    This is what a properly turned on server looks like
        ![](https://imgur.com/a/VVgxEF1)

## Arguments to boot the server
    Use this method - start_server --"type a argument"

    The comment is general. You can normally use these arguments as given in the example above
    Argument:
        --b     <- daily backups
        --dl    <- logs deleted every 3 days
        --db    <- backup deleted every 7 days
        --c     <- checking if the server is on