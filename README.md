Python 3.10 is not yet supported on Raspbian OS in the official repos.
When upgraded manually by source the using some packages (e.g., NumPy and SciPy)
are not yet available as binaries for ARM V7.

This repo contains prepared python wheels that can be easily installed with:
```
pip3 install <name of the wheel>.whl
```

Ensure to have the wheel package installed `pip3 install wheel`.
