# devops-cheatsheet

### # Executing Remote Scripts from github

<table>
<tr><th>bash</th></tr>
<tr><td bgcolor="#000000">

<pre style="background-color:#000000;color:#EEEDF0">
curl -sSL https://raw.githubusercontent.com/hclpandv/bash-learning/master/colors.sh | bash
</pre>
  
</td></tr> </table>
<!---      -->

<table>
<tr><th>PowerShell</th></tr>
<tr><td bgcolor="#012456">

<pre style="background-color:#012456;color:#EEEDF0">
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/hclpandv/devops-cheatsheet/master/demo.ps1'))
</pre>
  
</td></tr> </table>
<!---      -->


