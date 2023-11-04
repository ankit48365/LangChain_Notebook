# luigi_wsl
//wsl$ 

Step 1 — Setup - luigi on Ubuntu WSL Windows

https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server


hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ sudo apt update
hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ sudo apt -y up
hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ python3 -V
Python 3.10.12

Now luigi install
https://www.digitalocean.com/community/tutorials/how-to-build-a-data-processing-pipeline-using-luigi-in-python-on-ubuntu-20-04

hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ sudo apt install python3.10-venv
hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ python3 -m venv luigi-venv
hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ . luigi-venv/bin/activate
(luigi-venv) hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ pip install wheel luigi beautifulsoup4 requests

Step 2 — Creating a Luigi Task

create helloWorld.py

    import luigi
    class HelloLuigi(luigi.Task):
        def output(self):
            return luigi.LocalTarget('hello-luigi.txt')
        def run(self):
            with self.output().open("w") as outfile:
                outfile.write("Hello Luigi!")

run as temp local-scheduler
(luigi-venv) hp-desk-ak-lx@hp-desk-ak:~/lnx_git/luigi_ubntu_wsl$ python -m luigi --module hello-world HelloLuigi --local-scheduler








