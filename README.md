<p align="center">
</p>
### I. Install dependencies: Node.js, Docker, Git.

<details>
<summary>On Windows</summary>

1. Enable [Hyper-V](https://learn.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v).
2. Install [Docker for Windows](https://docs.docker.com/desktop/install/windows-install/).
3. Install NodeJS LTS using the [official installer](https://nodejs.org/en/download).
4. Install [Git for Windows](https://git-scm.com/download/win).

In all installs it is OK to leave all the options at their default values. You will need a terminal to complete this tutorial - [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) bash is the preferred option.
</details>

<details>
<summary>On Mac</summary>

1. Install [Docker for Mac](https://docs.docker.com/desktop/install/mac-install/).
2. Install Git using the [installer](https://sourceforge.net/projects/git-osx-installer/) or by [other means](https://git-scm.com/download/mac).
3. Install NodeJS LTS using the [official installer](https://nodejs.org/en/download).
</details>

On Linux or Code spaces

### II. QUICK START 

Open a terminal and run

```
sudo apt update
```
```
sudo apt install git
```
```
sudo apt install nodejs
```

```
sudo apt install npm
```

```
npm install -g npm@10.2.0
```
```
sudo apt-get install ca-certificates curl gnupg lsb-release -y
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
```
```bash
git clone https://github.com/Dwanx-9/Squid-quest-all.git
```
```
cd Subsquid-quest-all/Subsquid
```
```
npm config set prefix ~/Subsquid
```
```
export PATH="${HOME}/Subsquid/bin:$PATH"
```

```
npm install --global @subsquid/cli@latest
```

### Quest Single Proc !!!

```
cd my-single-chain-squid
```
```
npm config set prefix ~/my-single-chain-squid
```
```
export PATH="${HOME}/my-single-chain-squid/bin:$PATH"
```
```
npm install --global @subsquid/cli@latest
```

<details>
<summary>>upload .Key</summary>
Press "Get Key" button in the quest card to obtain the `singleProc.key` key file. Save it to the `./query-gateway/keys` subfolder of the squid folder. The file will be used by the query gateway container.

</details>

### Running !!!
```
sqd up
npm ci
sqd build
sqd migration:apply
```
```
sqd run .
```
If the quest process is 100% complete and claim it. next Proc. key

### Stop running !!!

CTRL + C
```
sqd down
```
### Quest Double Proc !!!
```
cd ..
```
```
cd my-double-proc-squid
```
```
npm config set prefix ~/my-double-proc-squid
```
```
export PATH="${HOME}/my-double-proc-squid/bin:$PATH"
```
```
npm install --global @subsquid/cli@latest
```
<details>
<summary>Creat Keys</summary>
   go to `doubleProc.key` >>> add folder name `keys`
Press "Get Key" button in the quest card to obtain the `doubleProc.key` key file
   in Subsquid quest. Upload to`./query-gateway/keys` subfolder of the squid folder. The file will be used by the query gateway container.
</details>

### Running !!!
```
sqd up
npm ci
sqd build
sqd migration:apply
```
sqd run .
```
If the quest process is 100% complete and claim it. next Proc. key

### Stop running !!!

CTRL + C
```
```
sqd down
```
### Quest Triple Proc !!!
```
cd ..
```
```
cd my-triple-proc-squid
```
```
npm config set prefix ~/my-triple-proc-squid
```
```
export PATH="${HOME}/my-triple-proc-squid/bin:$PATH"
```
```
npm install --global @subsquid/cli@latest
```

<details>
<summary>>upload .Key</summary>
Press "Get Key" button in the quest card to obtain the `tripleProc.key` key file. Save it to the `./query-gateway/keys` subfolder of the squid folder. The file will be used by the query gateway container.

</details>

### Running !!!
```
sqd up
npm ci
sqd build
sqd migration:apply
```
sqd run .
```
If the quest process is 100% complete and claim it. next Proc. key

### Stop running !!!

CTRL + C
```
```
sqd down
```

### Quest Quad Proc 
```
cd ..
```
```
cd my-quad-proc-squid
```
```
npm config set prefix ~/my-quad-proc-squid
```
```
export PATH="${HOME}/my-quad-proc-squid/bin:$PATH"
```
```
npm install --global @subsquid/cli@latest
```
<details>
<summary>>upload Key quadproc.key</summary>
Press "Get Key" button in the quest card to obtain the `quadProc.key` key file. Save it to the `./query-gateway/keys` subfolder of the squid folder. The file will be used by the query gateway container.
</details>

### Running

```
sqd up
npm ci
sqd build
sqd migration:apply
```
sqd run .
```
If the quest process is 100% complete and claim it. next Proc. key

### Stop running

CTRL + C
```
```
sqd down
```

### The command should output lines like these:
   ```
   [api] 09:56:02 WARN  sqd:graphql-server enabling dumb in-memory cache (size: 100mb, ttl: 1000ms, max-age: 1000ms)
   [api] 09:56:02 INFO  sqd:graphql-server listening on port 4350
   [processor] 09:56:04 INFO  sqd:processor processing blocks from 6000000
   [processor] 09:56:05 INFO  sqd:processor using archive data source
   [processor] 09:56:05 INFO  sqd:processor prometheus metrics are served at port 33097
   [processor] 09:56:08 INFO  sqd:processor:mapping Burned 59865654 Gwei from 6000000 to 6016939
   [processor] 09:56:08 INFO  sqd:processor 6016939 / 17743832, rate: 5506 blocks/sec, mapping: 304 blocks/sec, 182 items/sec, eta: 36m
   ```
   The squid should sync in 10-15 minutes. When it's done, stop it with Ctrl-C, then stop and remove the auxiliary containers with
   ```bash
