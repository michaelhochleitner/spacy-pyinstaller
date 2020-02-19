
pip install https://github.com/pyinstaller/pyinstaller/archive/develop.zip  
pyinstaller nlp.spec  
./dist/nlp/nlp  
```
Traceback (most recent call last):  
  File "nlp.py", line 1, in <module>  
    import spacy  
  File "/home/mh/spacy-pyinstaller/venv/lib/python3.6/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module  
    exec(bytecode, module.__dict__)  
  File "spacy/__init__.py", line 10, in <module>  
  File "/home/mh/spacy-pyinstaller/venv/lib/python3.6/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module  
    exec(bytecode, module.__dict__)  
  File "thinc/neural/__init__.py", line 4, in <module>  
  File "/home/mh/spacy-pyinstaller/venv/lib/python3.6/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module  
    exec(bytecode, module.__dict__)  
  File "thinc/neural/_classes/model.py", line 11, in <module>  
  File "/home/mh/spacy-pyinstaller/venv/lib/python3.6/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module  
    exec(bytecode, module.__dict__)  
  File "thinc/neural/train.py", line 7, in <module>  
  File "optimizers.pyx", line 14, in init thinc.neural.optimizers  
  File "ops.pyx", line 24, in init thinc.neural.ops  
ImportError: cannot import name _custom_kernels  
[16858] Failed to execute script nlp  
```
