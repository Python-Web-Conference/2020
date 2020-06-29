Solution to #1 & #2: https://github.com/rsyring/pyweb-flog/commit/6d882cca816ab113e5d16584ce3d9afb64b8556c
Note that I chose to return a string from process_profile.  That causes me problems when I work on #5 and I change to returning data.  But then for #8, I come back to returning the string.  This kind of iterative development is exactly what we are looking for.  At each step of the way, I understand a little more about the problem and make relatively small changes to accomodate.  The best architecture ends up revealing itself and I build up my test cases and look for an elegant and maintainable solution that solves all test cases.
It also gives me confidence as I refactor.  As long as I trust my tests, and they aren't failing, I can be confident my refactor didn't accidentally break things.  That lets me focus my attention during the refactor on the software architecture (solid, dry, etc.) and not on what might be breaking as a result of it.

Solution to #3 & #4: https://github.com/rsyring/pyweb-flog/commit/aeb4b3387db252e0c168a18ea20ab2f35aef4222
Two commits make up the solution to 3 & 4: https://github.com/rsyring/pyweb-flog/compare/6d882cca816ab113e5d16584ce3d9afb64b8556c...b6af9838459bf6a69af38a0e115ea983b94aac55

Solutions for test 5: https://github.com/rsyring/pyweb-flog/commit/88602a6d221dadc9a1be28573cf4a2cfb0da4cae
If you checkout the branch at that commit and run the tests, you will see it actually fails.  Turns out, I had to bypass Flask-Mail's helpful feature of not sending emails live during testing.  I did that with a Pytest fixture: https://github.com/rsyring/pyweb-flog/commit/660c6abcc17824e9f9fad8faa3ca850d4d070908
