# pytest_test
A stable and simple example of pytest on a simple module. Or that is the goal. I've been trying to setup a very basic test harness for pytest and have been failing at it. The silver lining here is that I'm not the only person and this question is asked frequently on places like stack over flow.

e.g.:

- http://stackoverflow.com/questions/10253826/path-issue-with-pytest-importerror-no-module-named-yadayadayada
- http://stackoverflow.com/questions/20985157/py-test-no-module-named
- http://stackoverflow.com/questions/29164213/py-test-doesnt-find-module
- http://stackoverflow.com/questions/16945091/module-import-error-running-py-test-with-modules-on-path

I want to make this repo a definitive-working-version of a basic test harness.

# Current Issues I'm having

Basically.. py.test (and thus tox) cannot find my modules. I've tried setting PYTHONPATH to no avail.

    mbp0 pytest_test[master+*] $ py.test
    ======================================= test session starts =======================================
    platform darwin -- Python 2.7.11, pytest-2.9.2, py-1.4.31, pluggy-0.3.1
    rootdir: /Users/jmacdonald/w/pytest_test, inifile:
    collected 0 items / 1 errors

    ============================================= ERRORS ==============================================
    __________________________ ERROR collecting tests/test_syntax_errors.py ___________________________
    tests/test_syntax_errors.py:2: in <module>
        import mymodule
    E   ImportError: No module named mymodule
    ===================================== 1 error in 0.13 seconds =====================================
    mbp0 pytest_test[master+*] $ tox
    py27 installed: boto3==1.3.1,botocore==1.4.37,docutils==0.12,futures==3.0.5,jmespath==0.9.0,py==1.4.31,pytest==2.9.2,python-dateutil==2.5.3,six==1.10.0
    py27 runtests: PYTHONHASHSEED='3183506784'
    py27 runtests: commands[0] | py.test
    ======================================= test session starts =======================================
    platform darwin -- Python 2.7.11, pytest-2.9.2, py-1.4.31, pluggy-0.3.1
    rootdir: /Users/jmacdonald/w/pytest_test, inifile:
    collected 0 items / 1 errors

    ============================================= ERRORS ==============================================
    __________________________ ERROR collecting tests/test_syntax_errors.py ___________________________
    tests/test_syntax_errors.py:2: in <module>
        import mymodule
    E   ImportError: No module named mymodule
    ===================================== 1 error in 0.17 seconds =====================================
    ERROR: InvocationError: '/Users/jmacdonald/w/pytest_test/.tox/py27/bin/py.test'
    _____________________________________________ summary _____________________________________________
    ERROR:   py27: commands failed
    mbp0 pytest_test[master+*] $
