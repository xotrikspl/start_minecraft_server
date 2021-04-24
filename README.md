## start_minecraft_server

# Open /usr/bin/start_server
    * 

# To turn on the server automatically after restarting the server(VPS/VDS) you must do move files
    * /usr/lib/systemd/system/start_service.service
    (console) * chmod -R 755 /usr/lib/systemd/system/start_service.service

# Arguments to boot the server
    # stop, start and restart you know what it is for
    # You must shut down the server to use these arguments...
    // How to use? Use this method - cd /usr/bin/ && start_server --type a argument
        - auto_backup
        - auto_clear_logs

# All errors is save in this location
    # /tmp/minecraft_server