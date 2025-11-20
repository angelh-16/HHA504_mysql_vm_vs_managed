# Setup Steps For Managed MySQL Using Cloud SQL (GCP)
## Cloud SQL creation
1. Select "Create Sandbox instance"
2. Give it an Instance ID: sql and a password: passworD1*
3. Chose a region
4. Click into Customize your instance
5. Go under Machine configuration
6. Select Share core and 1 vCPU, 0.614 GB
7. Leave everything else on default
8. Create instance
![screenshot](../images/managed/v1.png)

## Configuration
1. Open the instance
2. Go to connections and find authorized Networks
3. Add a network with a name and 0.0.0.0/0
4. Click save
![screenshot](../images/managed/v3.png)

## Cloud Shell
1. connect via root user using `gcloud sql connect sql --user=root --quiet` and enter password
2. Once connected:
`CREATE DATABASE ahh;`
`CREATE USER 'angel'@'%' IDENTIFIED BY 'passworD1*';`
`GRANT ALL PRIVILEGES ON ahh.* TO 'angel'@'%';`
`FLUSH PRIVILEGES;`
![screenshot](../images/managed/v2.png)
![screenshot](../images/managed/v4.png)
3. Run the pyton code
    * My code ran into errors and could not connect. It took a while to figure out that I needed to changemy instance SSL mode to "Allow unencrypted network traffic (not recommended)" in order for my code to work.
![screenshot](../images/managed/v5.png)
![screenshot](../images/managed/v6.png)



