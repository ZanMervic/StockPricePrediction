# Stock trend prediction using machine learning (LSTM)

## Setting up the python virtual environment

Create the environment
```
python -m venv <venv_name>
```

Activate the environment (different for each platform)
```
bash/zsh
$ source <venv>/bin/activate

fish
$ source <venv>/bin/activate.fish

csh/tcsh
$ source <venv>/bin/activate.csh

PowerShell
$ <venv>/bin/Activate.ps1

cmd.exe
C:\> <venv>\Scripts\activate.bat

PowerShell
PS C:\> <venv>\Scripts\Activate.ps1
```

Every library that we will use in this environment we need to include in requirements.txt
So when we open this project on a new pc, we just create a new environment and install
all the libraries using the following command:

```
pip install -r requirements
```