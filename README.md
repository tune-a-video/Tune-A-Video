# Anonymous GitHub for Tune-A-Video

<p align="center">
<img src="./assets/teaser.gif" width="960px"/>  
<br>
<em><b>Tune-A-Video</b>: A novel T2V generator trained on one text-video pair and pretrained T2I models.</em>
</p>

# Table of Content
- [Anonymous GitHub for Tune-A-Video](#anonymous-github-for-tune-a-video)
- [Table of Content](#table-of-content)
- [Sample Results](#sample-results)
  - [Pretrained T2I (Stable Diffusion)](#pretrained-t2i-stable-diffusion)
  - [Personalized Pretrained T2I (DreamBooth)](#personalized-pretrained-t2i-dreambooth)
  - [Pretrained T2I with Pose Control (T2I-Adapter)](#pretrained-t2i-with-pose-control-t2i-adapter)
- [Baseline Comparisons](#baseline-comparisons)
- [Ablation Study](#ablation-study)

# Sample Results

## Pretrained T2I (Stable Diffusion)

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
  <td width=25% style="text-align:center;"><b></b></td>
  <td width=25% style="text-align:center;"><b></b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/man-basketball.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/man-basketball/bond.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/man-basketball/astronaut.gif"></td>              
  <td><img src="./assets/results/tuneavideo/sd/man-basketball/ironman.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A man is dribbling a basketball"</td>
  <td style="text-align:center;">"James Bond is dribbling a basketball on the beach"</td>
  <td style="text-align:center;">"An astronaut is dribbling a basketball, cartoon style"</td>
  <td style="text-align:center;">"Iron Man is dribbling a basketball on the lawn"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/man-skiing.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/man-skiing/spiderman-beach.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/man-skiing/wonder-woman.gif"></td>              
  <td><img src="./assets/results/tuneavideo/sd/man-skiing/pink-sunset.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A man is skiing"</td>
  <td style="text-align:center;">"Spider Man is skiing on the beach, cartoon style"</td>
  <td style="text-align:center;">"Wonder Woman, wearing a cowboy hat, is skiing"</td>
  <td style="text-align:center;">"A man, wearing pink clothes, is skiing at sunset"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/rabbit-watermelon.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/rabbit-watermelon/rabbit.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/rabbit-watermelon/cat.gif"></td>              
  <td><img src="./assets/results/tuneavideo/sd/rabbit-watermelon/puppy.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A rabbit is eating a watermelon on the table"</td>
  <td style="text-align:center;">"A rabbit is <del>eating a watermelon</del> on the table"</td>
  <td style="text-align:center;">"A cat with sunglasses is eating a watermelon on the beach"</td>
  <td style="text-align:center;">"A puppy is eating a cheeseburger on the table, comic style"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/lion-roaring.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/lion-roaring/tiger-roar.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/lion-roaring/lion-vangogh.gif"></td>              
  <td><img src="./assets/results/tuneavideo/sd/lion-roaring/wolf-nyc.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A lion is roaring"</td>
  <td style="text-align:center;">"A tiger is roaring"</td>
  <td style="text-align:center;">"A lion is roaring, Van Gogh style"</td>
  <td style="text-align:center;">"A wolf is roaring in New York City"</td>
</tr>
<!-- </table> -->

<!-- <details><summary><b>CLICK ME FOR MORE EXAMPLES</b></summary> -->
<!-- <table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
  <td width=25% style="text-align:center;"><b></b></td>
  <td width=25% style="text-align:center;"><b></b></td>
</tr> -->
<tr>
  <td><img src="./assets/results/data/bear.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/bear/bear.gif"></td>      
  <td><img src="./assets/results/tuneavideo/sd/bear/snow.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/bear/cartoon.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A brown bear walking on some rocks"</td>
  <td style="text-align:center;">"A brown bear walking <del>on some rocks</del>"</td>
  <td style="text-align:center;">"A brown bear walking on the snow"</td>
  <td style="text-align:center;">"A brown bear walking on some rocks, cartoon style"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/drift-turn.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/drift-turn/smoke.gif"></td>      
  <td><img src="./assets/results/tuneavideo/sd/drift-turn/van.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/drift-turn/desert.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A car is drifting on a track with smoke coming out of it"</td>
  <td style="text-align:center;">"A car is drifting on a track <del>with smoke coming out of it</del>"</td>
  <td style="text-align:center;">"A white van is drifting on a track with smoke coming out of it"</td>
  <td style="text-align:center;">"A car is drifting on the desert with smoke coming out of it"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/mbike-santa.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/mbike-santa/spider-man.gif"></td>      
  <td><img src="./assets/results/tuneavideo/sd/mbike-santa/sleigh-car.gif"></td>
  <td><img src="./assets/results/tuneavideo/sd/mbike-santa/cartoon.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A man dressed as Santa Claus riding a motorcycle"</td>
  <td style="text-align:center;">"Spider Man riding a motorcycle"</td>
  <td style="text-align:center;">"A man dressed as Santa Claus riding a sleigh car"</td>
  <td style="text-align:center;">"A man dressed as Santa Claus riding a motorcycle, cartoon style"</td>
</tr>
</table>
<!-- </details> -->

## Personalized Pretrained T2I (DreamBooth)

<img src="./assets/results/tuneavideo/personalized/modern-disney.png" width="240px"/>  


<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
  <td width=25% style="text-align:center;"><b></b></td>
  <td width=25% style="text-align:center;"><b></b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/man-basketball.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/man-basketball/mickey-mouse.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/man-basketball/panda.gif"></td>      
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/man-basketball/prince.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A man is dribbling a basketball"</td>
  <td style="text-align:center;">"Mickey Mouse is dribbling a basketball, modern disney style"</td>
  <td style="text-align:center;">"A panda is dribbling a basketball on the beach, modern disney style"</td>
  <td style="text-align:center;">"A handsome prince with a shining crown is dribbling a basketball, modern disney style"</td>
</tr>
<tr>
  <td><img src="./assets/results/data/bear-guitar.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/bear-guitar/rabbit.gif"></td>      
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/bear-guitar/prince.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/modern-disney/bear-guitar/princess.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A bear is playing guitar"</td>
  <td style="text-align:center;">"A rabbit is playing guitar, modern disney style"</td>
  <td style="text-align:center;">"A handsome prince is playing guitar, modern disney style"</td>
  <td style="text-align:center;">"A magic princess with sunglasses is playing guitar on the stage, modern disney style"</td>
</tr>
</table>

<img src="./assets/results/tuneavideo/personalized/mr-potato-head.png" width="240px"/>  

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
  <td width=25% style="text-align:center;"><b></b></td>
  <td width=25% style="text-align:center;"><b></b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/bear-guitar.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/mr-potato-head/bear-guitar/sunglasses-beach.gif"></td>
  <td><img src="./assets/results/tuneavideo/personalized/mr-potato-head/bear-guitar/lego-snow.gif"></td>      
  <td><img src="./assets/results/tuneavideo/personalized/mr-potato-head/bear-guitar/van-gogh.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A bear is playing guitar"</td>
  <td style="text-align:center;">"Mr Potato Head, wearing sunglasses, is playing guitar on the beach"</td>
  <td style="text-align:center;">"Mr Potato Head, made of lego, is playing guitar on the snow"</td>
  <td style="text-align:center;">"Mr Potato Head is playing guitar in the starry night, Van Gogh style"</td>
</tr>
</table>



## Pretrained T2I with Pose Control (T2I-Adapter)

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/man-basketball.gif"></td>
  <td><img src="./assets/results/tuneavideo/pose/man-basketball/ironman.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">"A man is dribbling a basketball"</td>
  <td style="text-align:center;">"Iron Man is dribbling a basketball on the beach"</td>
</tr>

<tr>
  <td width=25% style="text-align:center;"><b>Input Pose</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
  <td width=25% style="text-align:center;"><b>Input Pose</b></td>
  <td width=25% style="text-align:center;"><b>Output Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/pose/man-basketball/dancing/pose.gif"></td>      
  <td><img src="./assets/results/tuneavideo/pose/man-basketball/dancing/video.gif"></td>
  <td><img src="./assets/results/tuneavideo/pose/man-basketball/running/pose.gif"></td>      
  <td><img src="./assets/results/tuneavideo/pose/man-basketball/running/video.gif"></td>
</tr>
<tr>
  <td style="text-align:center;">dancing</td>
  <td style="text-align:center;">"Iron Man is dancing on the beach"</td>
  <td style="text-align:center;">running</td>
  <td style="text-align:center;">"Iron Man is running on the beach"</td>
</tr>
</table>


# Baseline Comparisons

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/car-turn.gif"></td>
</tr>
<tr>
  <td width=25% style="text-align:center;"><b>CogVideo</b></td>
  <td width=25% style="text-align:center;"><b>Text2LIVE</b></td>
  <td width=25% style="text-align:center;"><b>Plug-and-Play</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>    
</tr>
<tr>
  <td><img src="./assets/results/cogvideo/car-turn/car-cartoon.gif"></td>
  <td><img src="./assets/results/text2live/car-turn/car-cartoon.gif"></td>  
  <td><img src="./assets/results/pnp/car-turn/car-cartoon.gif"></td>          
  <td><img src="./assets/results/tuneavideo/sd/car-turn/car-cartoon.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A jeep car is moving on road, cartoon style"</td>
</tr>
<tr>
  <td><img src="./assets/results/cogvideo/car-turn/porsche-beach.gif"></td>
  <td><img src="./assets/results/text2live/car-turn/porsche-beach.gif"></td>  
  <td><img src="./assets/results/pnp/car-turn/porsche-beach.gif"></td>          
  <td><img src="./assets/results/tuneavideo/sd/car-turn/porsche-beach.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A Porsche car is moving on the beach"</td>
</tr>
</table>

<table>
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/blackswan.gif"></td>
</tr>
<tr>
  <td width=25% style="text-align:center;"><b>CogVideo</b></td>
  <td width=25% style="text-align:center;"><b>Text2LIVE</b></td>
  <td width=25% style="text-align:center;"><b>Plug-and-Play</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>    
</tr>
<tr>
  <td><img src="./assets/results/cogvideo/blackswan/pelican.gif"></td>
  <td><img src="./assets/results/text2live/blackswan/pelican.gif"></td>  
  <td><img src="./assets/results/pnp/blackswan/pelican.gif"></td>          
  <td><img src="./assets/results/tuneavideo/sd/blackswan/pelican.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A pelican is swimming in the river"</td>
</tr>
<tr>
  <td><img src="./assets/results/cogvideo/blackswan/duck-cartoon.gif"></td>
  <td><img src="./assets/results/text2live/blackswan/duck-cartoon.gif"></td>  
  <td><img src="./assets/results/pnp/blackswan/duck-cartoon.gif"></td>          
  <td><img src="./assets/results/tuneavideo/sd/blackswan/duck-cartoon.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A duck is swimming in the river, cartoon style"</td>
</tr>
</table>


# Ablation Study

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/man-skiing.gif"></td>
</tr>
<tr>
  <td width=25% style="text-align:center;"><b>w/o ST-Attn</b></td>
  <td width=25% style="text-align:center;"><b>w/o inversion</b></td>
  <td width=25% style="text-align:center;"><b>w/o finetuning</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>    
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/astronaut/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/astronaut/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/astronaut/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/astronaut/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"An astronaut is skiing on the moon"</td>
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/minecraft/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/minecraft/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/minecraft/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/man-skiing/minecraft/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A minecraft man is skiing"</td>
</tr>
</table>

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/car-turn.gif"></td>
</tr>
<tr>
  <td width=25% style="text-align:center;"><b>w/o ST-Attn</b></td>
  <td width=25% style="text-align:center;"><b>w/o inversion</b></td>
  <td width=25% style="text-align:center;"><b>w/o finetuning</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>    
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/beach/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/beach/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/beach/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/beach/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A jeep car is moving on the beach"</td>
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/sports-car/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/sports-car/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/sports-car/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/car-turn/sports-car/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A sports car is moving on the road"</td>
</tr>
</table>

<table class="center">
<tr>
  <td width=25% style="text-align:center;"><b>Input Video</b></td>
</tr>
<tr>
  <td><img src="./assets/results/data/rabbit-watermelon.gif"></td>
</tr>
<tr>
  <td width=25% style="text-align:center;"><b>w/o ST-Attn</b></td>
  <td width=25% style="text-align:center;"><b>w/o inversion</b></td>
  <td width=25% style="text-align:center;"><b>w/o finetuning</b></td>
  <td width=25% style="text-align:center;"><b>Tune-A-Video</b></td>    
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/puppy/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/puppy/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/puppy/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/puppy/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A puppy is eating a cheeseburger on the table, comic style"</td>
</tr>
<tr>
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/cat/wo_attn.gif"></td>
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/cat/wo_inv.gif"></td>  
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/cat/wo_ft.gif"></td>          
  <td><img src="./assets/results/tuneavideo/ablation/rabbit-watermelon/cat/tuneavideo.gif"></td>
</tr>
<tr>
  <td style="text-align:center;" colspan="4">"A cat with sunglasses is eating a watermelon on the beach"</td>
</tr>
</table>