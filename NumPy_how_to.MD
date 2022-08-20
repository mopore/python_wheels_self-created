# System-wide Dependencies

```
sudo apt-get install python-dev libatlas-base-dev
```


# Ensure 5+ GB of RAM

On a Zero 2 a swap file is necessary
```
sudo dd if=/dev/zero of=/swap1 bs=1M count=5120
sudo mkswap /swap1
# This will take several minutes!
```
After that, add the following code into the end of /etc/fstab.
```
/swap1 swap swap
```


# Get Source, Compile and Install

```
# Get the sources (can be a few gigs)
git clone --recursive https://github.com/numpy/numpy  # Takes forever...
cd numpy
git checkout tags/v1.23.2
git submodule sync
git submodule update --init --recursive

# Build preperations
sudo apt update
sudo apt install cython make -y
pip3 install cython
sudo pip3 install wheel  # If not yet installed or an immediate problem occurs when trying to install

# Build NumPy - Took a few hours
python3 setup.py bdist_wheel

# Install 'wheel' on system level
sudo pip3 install dist/*.whl  # Should be done very swiftly
```


