---
title:  "Dusty"
layout: single
permalink: /robotics-projects/Dusty/
collection: robotics-projects
---

{% include figure image_path="/assets/images/robotics/Dusty.jpg" alt="Dusty" %}

One week before the ATMAE National Robotics Competition in 2015, we found that the robot we had been building, the Think Tank, wasn't able to make it over the very first obstacle in the obstacle course. Terrified that we would receive no points on the obstacle course, we scrapped the Think Tank and started looking for a solution. There was one thing on the Think Tank that worked well, the dustpan scooper that we made for picking up objects. Running out of time, we took the thing that worked and made a robot out of it, and that robot was Dusty.

The ATMAE National Robotics Competition is held by the Association of Technology, Management, and Applied Engineering every year, and typically is typically an obstacle course and task based competition, but the rules change every year. In 2015 those rules were go through an obstacle course featuring a burlap sack draped over PVC, a teeter totter, autonomously picking up blocks that spell out ATMAE, then going backwards through the obstacle course to the beginning and spelling out ATMAE with the collected blocks.

{% include figure image_path="/assets/images/robotics/burlap_sack.jpg" alt="The Burlap Sack" %}

The burlap sack proved to be an extremely difficult task. Due to the way it was draped over the PVC pipe, the weight of the robot would cause the burlap to sag such that the incline became almost vertical near the top. The Think Tank would end up tipping over backwards and rolling onto its side, resulting in a loss of points to right the robot.

{% include figure image_path="/assets/images/robotics/dusty_teeter_totter.jpg" alt="Teeter totter" %}

Since the Think Tank wasn't able to get over the burlap sack, the very first obstacle, we focused on building a robot that would do that first and everything else later. At the time, there was no rule stating that three failures to make it over an obstacle would permit skipping it with a penalty, so we thought if we didn't make it over the burlap sack in three tries, we would get zero points on the obstacle course. We envisioned a robotic dustpan with wheels larger than its body, making it difficult to flip over.

{% include figure image_path="/assets/images/robotics/dusty_prototype.jpg" alt="Prototype of Dusty" %}

With only a week until competition, and most of our suppliers not shipping fast enough, Dusty was made entirely from scrap pieces we had lying around or could find at a local hardware store. We focused heavily on rapid iterative development for the design of Dusty. With the short time frame, we couldn't follow the more typical engineering practices we did when building the Think Tank. Fortunately, we had built the obstacles so we could test out the robot, see what works, see what doesn't, and improve from there. Dusty needed to be wide enough to pick up the blocks but had to fit in a 12 inch by 12 inch area. The only wheels we had that were thin enough for the required dustpan area and still fit in the box were omni wheels. To prevent sliding, we hot glued the rollers in place, hammered nails into the rollers for traction on the burlap sack, and placed rubber bands between the rollers for traction on the teeter totter. The electronics stuck sightly out of the top of Dusty, which made driving inverted more difficult, but this was a real problem since we would still tumble down the burlap sack when going down. To fix this, we added a self-righting mechanism so Dusty could flip right side up without a penalty from righting it ourselves. 

The software for Dusty was quite simple. We took all the electronics from the Think Tank, and removed a lot of the complexity, meaning the software required very little work. The only addition was the self-righting mechanism which was activated by the press of a button. The autonomous line following used the same infrared sensors as the Think Tank. Dusty was controlled just like the Think Tank. We used a wireless router and connected Dusty and a laptop with a controller to the Wi-Fi, allowing us to wirelessly communicate with Dusty. This solution wasn't great, as there were many Wi-Fi signals in the area at the competition, and we would occasionally lose connection to Dusty.

{% include figure image_path="/assets/images/robotics/dusty_single.jpg" alt="Dusty before his sencond self righting servo" %}

I worked mostly on the mechanical design of Dusty, including making sheet metal parts for the chassis and getting the wheels to work by hot gluing and hammering nails into them. I helped with the software, but there wasn't much to do since nearly all the code was taken directly from the Think Tank.

Perhaps our largest emergency came the night before we left to go to the competition. One of the gearboxes for the drive motors broke completely and needed to be replaced. We didn't have spare gearboxes around, but we needed to find a solution. The next day, while driving to the competition, we stopped at a hardware store, and purchased an electric hand drill. We took the gearbox out of the hand drill, retrofitted it onto Dusty, modified the code to account for the difference in speed between the left and right gearboxes, and had everything working the night we arrived.

{% include figure image_path="/assets/images/robotics/dusty_relay.jpg" alt="Dusty at the competition" %}

Dusty ended up getting first place for the obstacle course and second place overall. The obstacle course was an easy win for Dusty. Dusty was the only robot at the competition capable of getting over the burlap sack and one of the two robots that was able to pick up the blocks. At the competition, when it was apparent nobody else was going to make it over the burlap sack, they changed the rules allowing robots to skip obstacles that they cannot surpass. Most of the robots were only able to go up and down the teeter totter. Dusty did not win first place overall, because the ATMAE National Robotics Competition is more than just a design challenge. It's more of an engineering challenge, meaning teams are expected to have a full portfolio detailing the design of the robot. This portfolio is due two weeks before the competition, meaning the judges had a portfolio for an entirely different robot. That didn't go over well, as the judges gawked at our horrific robot cobbled together from spare parts. We ended up scoring poorly in most of the other categories, but our high score from the obstacle course allowed us to get second place overall. Ultimately, we could have scored better had we taken the Think Tank to the competition, but I'm proud of Dusty and I feel like we made the right call starting from scratch a week before competition.

<iframe width="420" height="315"
    src="https://www.youtube.com/embed/-j4SRGuBUaA">
</iframe> 