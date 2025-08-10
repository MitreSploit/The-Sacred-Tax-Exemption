# Setup
I like to use authenticate through browser.
So to set that up, I use
```PowerShell
PS> git config --global credential.helper manager-core
```

Then I usually clone the repo immediately. 
```PowerShell
PS> git clone https://github.com/MitreSploit/The-Sacred-Tax-Exemption.git
```

Changing between branches can be accomplished like this.
```PowerShell
# Switch to master
PS> git checkout master

# Switch to Dev
PS> git checkout Development-Branch
```

Sometimes I've had conflicts between dev branch and master. If I accidently make a slight change to master but all my work is on the dev branch, then things usually go bad. 

I've been able to fix this with force
```PowerShell
PS> git checkout Development-Branch
PS> git push origin master --force
```

**This is usually enough to force the changes I want. **

