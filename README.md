# HackTM-OSINT-Old-Times-Writeup

<b>There are rumors that a group of people would like to overthrow the communist party. Therefore, an investigation was initiated under the leadership of Vlaicu Petronel. Be part of this ultra secret investigation, help the militia discover all secret locations and you will be rewarded.

Author: Legacy + FeDEX<br/>
Flag Format: HackTM{SECRET}</b><br/>

A quick google search for Vlaicu Petronel points to a twitter account with the handle of @PetronelVlaicu.
Nothing is of use on their live Twitter feed, but there are two deleted tweets found in the Way Back Machine:
![image](https://user-images.githubusercontent.com/54376366/73598824-1d299a80-44fa-11ea-914a-d366e24b986f.png)
![image](https://user-images.githubusercontent.com/54376366/73598852-6f6abb80-44fa-11ea-87f8-f9ad2b2867ee.png)

These Tweets are a link to the following google doc:
(https://docs.google.com/document/d/1XhgPI0jpK8TjSMmSQ0z5Ozcu7EIIWhlXYQECJ7hFa20/edit)
![image](https://user-images.githubusercontent.com/54376366/73598881-a6d96800-44fa-11ea-9f76-e29c220984e0.png)

In small font, there is a screen name of E4gl3OfFr3ed0m.
![image](https://user-images.githubusercontent.com/54376366/73599303-1ea99180-44ff-11ea-8bee-d729aaba2a4a.png)

E4gl3OfFr3ed0m is a GitHub username. Investigating the commit history shows a link and some PHP code:
https://github.com/E4gl3OfFr3ed0m/resistance/commits?author=E4gl3OfFr3ed0m

![image](https://user-images.githubusercontent.com/54376366/73598933-3e3ebb00-44fb-11ea-93fe-90467445b5e5.png)
![image](https://user-images.githubusercontent.com/54376366/73598946-69290f00-44fb-11ea-9037-562c4144269e.png)


Invoking a WebRequest for all regions gets a list of 129 coordinates:
```sh
0..128 | % { (iwr http://138.68.67.161:55555/spread_locations.php/?region=$_).Content }
```
<i>22.5277957,47.3561089<br/>
22.5497683,47.184652<br/>
22.5277957,47.0276192<br/>
...</i>

Finally to insert the coordinates into copypastemap.com and reveal the flag:

![image](https://user-images.githubusercontent.com/54376366/73598730-21a18380-44f9-11ea-9b89-def4cc76a3b1.png)

<b>HackTM{HARDTIMES}</b>
