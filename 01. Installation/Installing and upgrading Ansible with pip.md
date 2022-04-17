# Ansible can be installed on many systems with pip, the Python package manager

## Prerequisites: Installing pip
If pip is not already available on your system, run the following commands to install it:

    curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
    python get-pip.py --user
    
# Installing Ansible with pip
    python -m pip install --user ansible

# Installing Ansible in a virtual environment with pip
    python -m virtualenv ansible  # Create a virtualenv if one does not already exist
    source ansible/bin/activate   # Activate the virtual environment
    python -m pip install ansible
    
# Upgrading Ansible with pip
    pip uninstall ansible
    pip install ansible

# Confirming your installation
    ansible all -m ping --ask-pass
    ansible all -m ping # withou pass
