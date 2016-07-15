# pytest_test

The goal of this repository is to provide a simple working example of tox and py.test.

As with many things I do, I often solve my own issues when I start thinking out loud. i.e. When I start typing out my actual issues, the solution becomes apparent to me.

During the creation of this repository I actually solved my misunderstandings with py.test and tox. See the links below, I'm not the only one to have encountered issues.

- http://stackoverflow.com/questions/10253826/path-issue-with-pytest-importerror-no-module-named-yadayadayada
- http://stackoverflow.com/questions/20985157/py-test-no-module-named
- http://stackoverflow.com/questions/29164213/py-test-doesnt-find-module
- http://stackoverflow.com/questions/16945091/module-import-error-running-py-test-with-modules-on-path

## How-to run these examples

My initial motivation for testing my code was that I had misspelled an imported module in a script that I was writing for work.

If you edit mymodule.py and remove the b from "boto3" you will see the commands below fail. And this is a good thing. Likewise if you would like to see an actual test fail, simple edit tests/test_syntax_errors.py and change 1 == 1 to 1 == 0.

### py.test

    mbp0 pytest_test[master+*] $ PYTHONPATH=. py.test
    ========================== test session starts ==========================
    platform darwin -- Python 2.7.11, pytest-2.9.2, py-1.4.31, pluggy-0.3.1
    rootdir: /Users/jmacdonald/w/pytest_test, inifile:
    collected 1 items

    tests/test_syntax_errors.py .

    ======================= 1 passed in 0.11 seconds ========================
    mbp0 pytest_test[master+*] $

### tox

    mbp0 pytest_test[master+*] $ tox
    py27 installed: boto3==1.3.1,botocore==1.4.37,docutils==0.12,futures==3.0.5,jmespath==0.9.0,py==1.4.31,pytest==2.9.2,python-dateutil==2.5.3,six==1.10.0
    py27 runtests: PYTHONHASHSEED='713732044'
    py27 runtests: commands[0] | py.test
    ========================== test session starts ==========================
    platform darwin -- Python 2.7.11, pytest-2.9.2, py-1.4.31, pluggy-0.3.1
    rootdir: /Users/jmacdonald/w/pytest_test, inifile:
    collected 1 items

    tests/test_syntax_errors.py .

    ======================= 1 passed in 0.11 seconds ========================
    ________________________________ summary ________________________________
      py27: commands succeeded
      congratulations :)
  mbp0 pytest_test[master+*] $
