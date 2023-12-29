<h1>CTF - Bypassing Deny Lists</h1>

<h2>Scenario</h2>
<a href='https://tryhackme.com/room/picklerick'>https://tryhackme.com/room/picklerick</a><br><br>
<img width="1146" alt="Screen Shot 2023-12-29 at 18 14 21" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/56e862a7-9cdd-4c92-a802-576fabc19802">

<h2>First Ingredient</h2>
<h3>Scanning</h3>
My exploration began by scanning the machine, revealing open <b>ports 22 (SSH) and 80 (HTTP)</b>. The website hosted on port 80 was my initial focus for enumeration.<br><br>
<img width="1153" alt="Screen Shot 2023-12-29 at 18 21 07" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/cdbdb246-f6e7-42a5-9bd4-ea318fb70241">

<h3>Enumerating Services</h3>
Reviewing the source code of the webpage at <b>HTTP://10.10.5.162</b> unveiled the username - R1ckRule3s.<br><br>
<img width="1155" alt="Screen Shot 2023-12-29 at 18 23 16" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/bb15a643-ec26-477e-be90-b2a0011ba23e">

<h2>Second Ingredient</h2>
<h3>Identifying Hidden Directories</h3>
Utilising the gobuster command, I uncovered hidden directories within the site. Further exploration led me to the <b>robots.txt</b> file, revealing a password alongside the previously identified username.<br><br>
<img width="1156" alt="Screen Shot 2023-12-29 at 18 31 49" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/de39c752-4fa7-4ca9-a4b6-fdc529f58d15"><br><br>
<img width="1155" alt="Screen Shot 2023-12-29 at 18 33 50" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/63967493-55ec-4d99-bec5-def7c16d31f7"><br><br>
<img width="1148" alt="Screen Shot 2023-12-29 at 18 33 52" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/e96d5a8c-0544-4efa-9d1e-3c4327d8ff1d"><br><br>
With both username and password, logging in redirected me to <b>portal.php</b> featuring a command panel. By executing the <b>ls</b> command, I accessed a file containing the first secret ingredient in a file named <b>Sup3rS3cretPickl3Ingr3d.txt</b>.<br><br>
<img width="1153" alt="Screen Shot 2023-12-29 at 18 34 35" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/ff397db7-a01a-4e48-9a4b-e902e6e819b5"><br><br>
<img width="1152" alt="Screen Shot 2023-12-29 at 18 35 21" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/d198572b-c128-4450-ae8c-8f25186c00cc"><br><br>
<img width="1153" alt="Screen Shot 2023-12-29 at 18 36 08" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/6e103bf6-0aca-4fd3-8025-5f1abfc9604f">

<h3>Digging Further</h3>
Exploring a file named <b>clue.txt</b> and navigating through directories, specifically <b>/home/rick</b>, led to a file named <b>second ingredients</b>. Although the <b>cat</b> command was disabled, using the <b>less</b> command displayed the file contents.<br><br>
<img width="1154" alt="Screen Shot 2023-12-29 at 18 37 27" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/45ae86e9-9eae-42c3-8ed7-90d41dd6e457"><br><br>
<img width="1160" alt="Screen Shot 2023-12-29 at 18 38 48" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/0ae74657-762c-41a8-9153-07451218e20a"><br><br>
<img width="1151" alt="Screen Shot 2023-12-29 at 18 39 40" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/65afb2ed-0288-4ccc-ba60-3e9cb26c1989"><br><br>
<img width="1152" alt="Screen Shot 2023-12-29 at 18 40 17" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/52760728-82aa-4231-b536-444a4ac931c5"><br><br>
<img width="1153" alt="Screen Shot 2023-12-29 at 18 41 45" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/6ef52fcc-b3df-413c-a680-2654620d275b">

<h2>Third Ingredient</h2>
<h3>Accessing /root</h3>
Despite initial limitations in viewing contents in the <b>/root</b> directory, leveraging <b>sudo</b> with any command allowed access without a password prompt. Utilising <b>sudo ls /root</b>, I located the third ingredient. Employing <b>sudo less</b>, I successfully read the contents of the <b>3rd.txt</b> file.<br><br>
<img width="1152" alt="Screen Shot 2023-12-29 at 18 43 55" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/c3c7b557-6dd8-47ea-8ae7-09fb3e8f9adf"><br><br>
<img width="1149" alt="Screen Shot 2023-12-29 at 18 44 38" src="https://github.com/Rahul0902/bypassing-deny-lists/assets/44233038/4a328578-42c0-4b7d-9ea0-f17a453e76f5">

