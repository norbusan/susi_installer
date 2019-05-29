# Installation on Debian, Ubuntu, and other Debian based distributions

Tested on:
- Ubuntu 18.04, 18.10, 19.04
- Debian 9 Stretch, Debian 10 Buster
- Linux Mint 18.3 (10 July 2018)

### Steps

- Download the installer script and run it
```
$ wget https://raw.githubusercontent.com/fossasia/susi_installer/development/install.sh
$ bash install.sh
```

The installation will ask whether install necessary packages via `apt-get` and
`pip3 install` by using `sudo`. If you answer `y` at the prompt, all necessary
requirements should be installed automatically. If you answer `n`, then you 
need to install the requirements manually, they are mentioned in the installation
output.

### Installation location

By default installation is done for the current user and into the directory
`$HOME/SUSI.AI`. The installation mode can be changed by adding `--system` to
the `install.sh` invocation, which will install the components system-wide.

If you want to change the installation directory in single user mode, use
`--destdir`.

For details see the output of `install.sh --help`.

### Configuration



### Sound setup

- Verify that your Audio setup is done properly. For this, first we need to check for recording devices. Run command 
```
$ rec a.wav
```
Verify that it gives an output like below.

![Ubuntu Rec Command](images/ubuntu-rec.png)

- After this, play your recorded audio by running ```play a.wav```. It should give an output like below
and your audio must be audible to you.

![Ubuntu Play Command](images/ubuntu-play.png)

If you hear your voice properly and output is similar to what shown in screenshots, setup is 
done correctly. If you face an error, try running ```pulseaudio -D``` and re-running the commands.
If still there is error, see if devices are selected correctly in Ubuntu sound settings.

- Run the configuration generator script and optimize the setup according to your needs.
```bash
$ python3 config_generator.py
```
-Note: Enclose every input(y/n, email, password) queried after running the above command with ''(single quotes).

- One config.json is generated, you may run SUSI User Interface by executing the following command
```bash
$ python3 app.py
```
- Alternatively ,you can run SUSI without User Interface by executing the following command
```
$ python3 -m main
```

In both case SUSI will start in always listening Hotword Detection Mode. To ask SUSI a question, say "Susi". If detection of
hotword is successful, you will hear a small bell sound. Ask your query after the bell sound. Your query will be
processed by SUSI and you will hear a voice reply.

#### Faced any errors?

If you still face any errors in the setup, please provide a screenshot or logs of errors being encountered.
This would help rectify the issue sooner.

