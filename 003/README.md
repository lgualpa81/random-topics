
# Create a folder
mkdir actions-runner && cd actions-runner

# Download the latest runner package
curl -o actions-runner-linux-x64-2.328.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.328.0/actions-runner-linux-x64-2.328.0.tar.gz

# Extract the installer
tar xzf ./actions-runner-linux-x64-2.328.0.tar.gz

# Create the runner and start the configuration experience
./config.sh \
  --url https://github.com/<USER>/<REPO> \
  --token <YOUR_TOKEN> \
  --name wsl-runner-local \
  --labels self-hosted,linux,coder \
  --work _work \
  --replace

# Last step, run it!
./run.sh