# 2013 AWS Honeypot Attacks Visualisation

It is available to visit this visualisation in this [link](https://fang-zeqiang.github.io/2013_AWS_Honeypot_Attacks_Visualisation/) : )
I want to hear your feedback.

## Intro

This visualisation work is aiming to
present the cyber-attacks on Amazon web services (AWS) honeypot server from
March 2013 to September 2013 in US and the frequency of attack cases is counted
for 50 states. The key findings are shown below:

1. **TCP** is the most frequent use of cyber security protocol in 2013 attack events.
  But it is better to care about the small probability events happening
  because of the Murphy's law appear in server security protection such as
  ICMP protocol.
2. Most of attackers were in the
  western and eastern area such as California and New York. Although
  attackers such as individual hackers may utilise different servers in
  different places, it is meaningful for enterprises to trace the pattern of
  attacks. The top 10 states where attackers attempted most are given below:

| **Top 10 states in the frequency of attacks** |
| --- |
| California |
| Colorado |
| Florida |
| Missouri |
| Arizona |
| Pennsylvania |
| Illinois |
| New York |
| Washington |

## Design

The design idea of this work is from the perspectives of user portrait, colour matching, legibility and accuracy, interactivity, etc., to better show AWS honeypot attack data in the US. Firstly, the target audience for this work is server security practitioners and some non-technical personnel who are interested in network services. This work attempts to make a good balance between legibility and accuracy. Accuracy is reflected in that whenever the mouse hovers over any information point, the specific and accurate information of the attackers will be displayed in the bottom-left corner of the window. Lastly, the colour adopts the concept of contrast, such as blue versus yellow. I try to select a colour with lower saturation so that it is not easy to cause aesthetic fatigue.

## Technical Approach

Two map styles ("All Details" and "Frequency of Attacks for 50 States") were made in
Mapbox Studio. Then these two styles were imported into html file via mapbox-gl.js tool. Furthermore, click buttons were placed in top-left window to let users choose which layer they want to explore, and they can switch two different layers to compare easily. To achieve this function, addEventListener were applied in monitoring users' behaviours such as "click". Once they click the button, the switchLayer() will execute to switch different maps. Then the flyTo() method allow users can visit some interesting states such as California more directly. Most interesting part in technical approaches is the mousemove() function. This method can allow users to visit more accurate information about attackers who attack the host of AWS servers.

## Dataset

This dataset is from Kaggle, archived by Jacobs & Bob Rudis who worked in Amazon. The AWS Honeypot Database is an open-source database including information on cyber-attacks/attempts. The original data has 451,581 data points collected from 9:53pm on 3 March 2013 to 5:55am on 8 September 2013.
