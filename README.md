# Assignment 3 - Part 1


The goal of this assignment is to create a Bash script that generates a static `index.html` file that contains system information, the file runs daily at 05:00 using a `systemd` service and timer. The script that creates the HTML document will be ran on your Arch Linux and hosted from a `nginx` web server which has a `ufw` (uncomplicated firewall) to secure your server. 

## Table of Contents


## Task 1: Creation of System User 

1. Creating a new system user 

Copy the following command to create a system user 

```
sudo useradd -r -d /var/lib/webgen -s /usr/sbin/nologin webgen
```

-r creates a system account 

-d specifies the home directory

-s specifes a non login shell 

2. Copy and paste the following command to create a home directory. 

```
sudo mkdir -p /var/lib/webgen
```

Then, copy and paste the following command to create `bin` and `HTML` sub-directories in the webgen directory.

```
sudo mkdir -p /var/lib/webgen/bin /var/lib/webgen/HTML
```

3. Git clone repository. 

Copy and Paste the command below to gain the generate_index starter file. 

```
git clone https://git.sr.ht/~nathan_climbs/2420-as2-start

```
>[!NOTE]
Make sure to use `ls` command to verify if the repository is cloned.

4. Moving generate_index file to `/var/lib/webgen/bin` directory. 

```
sudo mv 2420-as2-start/generate_index /var/lib/webgen/bin/
```
>[!NOTE]
You must give `generate_index` permission to be executable. 

Copy and Paste the command to give it permission. 

``` 
sudo chmod +x /var/lib/webgen/bin/generate_index
```

5. Create the `index.html` file. 

Type the following command to `cd` into the `/webgen/HTML` directory. 

```
cd /var/lib/webgen/HTML/
```

Then run

```
sudo nvim index.html
```
>[!NOTE]
To see the directory structure, install tree by copying the following command

``` 
sudo pacman -S tree
```
then

```
tree /var/lib/webgen
```
This will show the structure of the new systems user home directory.

6. Setting ownership to webgen.

```
sudo chown -R webgen:webgen /var/lib/webgen
```

## Task 2: Creation of service and timer scripts













