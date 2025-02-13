Install necessary dependencies:

First install scoop:
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser \n
irm get.scoop.sh | iex

Then use scoop to install dependencies:

scoop bucket add nerd-fonts
scoop install Cascadia-Code

Then Navigate to your terminal’s settings.
Look for “Defaults” and then “Appearance.”
In the “Font Face” option, select “Cascadia-Code.”

scoop bucket add main
scoop install oh-my-posh

Now we install mods for powershell:
Install-Module -Name Terminal-Icons -Scope CurrentUser
Install-Module posh-git -Scope CurrentUser
Install-Module -Name PSReadLine -Scope CurrentUser

Finally we open the profile with this command:
notepad $profile

And add this configuration:

Import-Module posh-git
Import-Module -Name Terminal-Icons
Import-Module PSReadLine
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows

oh-my-posh --init --shell pwsh --config ~/AppData/Local/Programs/oh-my-posh/themes/mm-custom.omp.json | Invoke-Expression
