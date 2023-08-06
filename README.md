
## On a fresh clone
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
...
deactivate
```

Configure the Python interpreter in IntelliJ (with Python CE plugin) by selecting the python executable in the venv folder

### ref. [how to create deployable packages](https://www.infoworld.com/article/3656628/6-ways-to-package-python-apps-for-re-use.html)

## Build executable (discouraged, long startup time)
- Get into the virtualenv `source venv/bin/activate`
- `pip install pyinstaller`
- `pyinstaller -F -c --paths ./venv/lib/python3.11/site-packages ./gpx_to_sim.py`


## Standalone package with zipapp
- `cd utilities`
- `python -m pip install -r game_json_to_sim/requirements.txt --target game_json_to_sim`
- remove unneeded folders
- `python -m zipapp -p python game_json_to_sim`

