42 INFO: PyInstaller: 4.0.dev0+a1f92c6a08  
42 INFO: Python: 3.6.9  
43 INFO: Platform: Linux-4.15.0-88-generic-x86_64-with-Ubuntu-18.04-bionic  

```
pip install -U spacy
pip install https://github.com/pyinstaller/pyinstaller/archive/develop.zip  
pyinstaller nlp.spec  
./dist/nlp/nlp  
```

```
ImportError: cannot import name _custom_kernels
```
does not occur when the pyinstaller hook file hook-spacy.py is used. The hookspath is defined in nlp.spec.  Full error trace:
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

```
ModuleNotFoundError: No module named 'srsly.msgpack.util'
```
does not occur when the hiddenimport 'srsly.msgpack.util' is specified. Hidden imports are specified in nlp.spec. Full error trace:

```
Traceback (most recent call last):
  File "nlp.py", line 1, in <module>
    import spacy
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/spacy/__init__.py", line 10, in <module>
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/thinc/neural/__init__.py", line 4, in <module>
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/thinc/neural/_classes/model.py", line 7, in <module>
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/srsly/__init__.py", line 6, in <module>
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/srsly/_msgpack_api.py", line 6, in <module>
  File "/usr/local/lib/python3.7/site-packages/PyInstaller/loader/pyimod03_importers.py", line 489, in exec_module
    exec(bytecode, module.__dict__)
  File "site-packages/srsly/msgpack/__init__.py", line 6, in <module>
  File "_packer.pyx", line 7, in init srsly.msgpack._packer
ModuleNotFoundError: No module named 'srsly.msgpack.util'
[21887] Failed to execute script nlp
```
