Install necessary dependencies:

First install scoop: <br />
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser <br />
irm get.scoop.sh | iex

Then use scoop to install dependencies: <br />
scoop bucket add nerd-fonts <br />
scoop install Cascadia-Code

Then Navigate to your terminal’s settings. <br />
Look for “Defaults” and then “Appearance.” <br />
In the “Font Face” option, select “Cascadia-Code.” <br />

scoop bucket add main <br />
scoop install oh-my-posh

Now we install mods for powershell: <br />
Install-Module -Name Terminal-Icons -Scope CurrentUser <br />
Install-Module posh-git -Scope CurrentUser <br />
Install-Module -Name PSReadLine -Scope CurrentUser <br />

Finally we open the profile with this command: <br />
notepad $profile

And add this configuration:

Import-Module posh-git <br />
Import-Module -Name Terminal-Icons <br />
Import-Module PSReadLine <br />
Set-PSReadLineOption -PredictionSource History <br />
Set-PSReadLineOption -PredictionViewStyle ListView <br />
Set-PSReadLineOption -EditMode Windows <br />

oh-my-posh --init --shell pwsh --config ~/AppData/Local/Programs/oh-my-posh/themes/mm-custom.omp.json | Invoke-Expression
