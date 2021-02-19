## InstallOnMac

https://brew.sh/

brew install pyenv

brew install openssl readline sqlite3 xz zlib

echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc

(Optional) You can also brew install pyenv-virtualenv


Install Python with Homebrew
This step is optional since we’ll never use this python in a project, but it’s recommended for two reasons:
Reason 1: This Homebrew-installed python becomes a safety net in case we forget to switch to a pyenv-installed python, we won’t accidentally pollute the system python.
Reason 2: It becomes a place to install global packages with pipx. This allows you to switch between python versions at-will using pyenv while maintaining a consistent set of global utilities like flake8 and black that are always available and don’t pollute the global python.

# Install python 3.x
brew install python
# Install pipx to manage global packages
python3 -m pip install --user pipx
python3 -m userpath append ~/.local/bin
# Install global packages
python3 -m pipx install flake8
python3 -m pipx install black



pyenv install --list

pyenv install 3.7.6
Then set it as the global python version:
pyenv global 3.7.6



Poetry creates all your virtual environments automatically on-demand in a single directory by default. If you prefer your virtual environments to live in the same directory with the code (like a .venv directory in your project), you can run this command:
poetry config virtualenvs.in-project true



 gpip or gpip3 to override this protection and force a package to install globally.
