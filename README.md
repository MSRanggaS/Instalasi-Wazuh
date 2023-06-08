# Instalasi-Wazuh

## OS Windows
1. Download file instalasi wazuh disini -> https://packages.wazuh.com/4.x/windows/wazuh-agent-4.4.1-1.msi
2. Run Command Prompt as administrator
3. Pindah direktori cmd ke tempat dimana installer wazuh berada, seharusnya di folder Download
4. Run command berikut
    ```
    wazuh-agent-4.4.1-1.msi /q WAZUH_MANAGER="10.15.43.15"
    ```
5. pindah ke direktori C:\Program Files (x86)\ossec-agent
6. Run command berikut
    ```
    agent-auth.exe -m 10.15.43.15
    ```
7. Run command berikut
    ```
    NET START WazuhSvc
    ```
8. Apabila sudah selesai maka akan seperti ini
![Screenshot 2023-06-08 113230](https://github.com/MSRanggaS/Instalasi-Wazuh/assets/61416036/78c6900f-5ab7-44f7-9517-17c819c75f9a)


## OS Linux
1. Jalankan command berikut secara berurutan
    ```
    curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | apt-key add -

    echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list

    apt update

    WAZUH_MANAGER="10.15.43.15" apt-get install wazuh-agent

    systemctl daemon-reload

    systemctl enable wazuh-agent

    systemctl start wazuh-agent
    ```
