# About
This is a documentation for [TIC-80](https://tic80.com) API for getting updates and [carts](https://github.com/nesbox/TIC-80/wiki/.tic-File-Format).

# Documentation
At the moment of writing this documentation, the main site of TIC-80 is https://tic80.com and all the methods will be shown using this domain.

## Check the latest version
### Request: 
```GET /api/?fn=version```

### Response:
```
version="1.1.2837"
major=1
minor=1
patch=2837
```

## Get carts
### Request
```GET /api/?fn=dir&path=```

`path` is what it seems to be - the path to get list of
### Response:
```
folders = 
{
	{ name = "Play" },
	{ name = "Devs" },

}

files = 
{
	{ name = "Pocket Hang On.tic", hash = "902a4ca7da42ca4385a0028e29689a1d", id = 3786, filename = "pocket_hang_on.tic"}, 
	{ name = "knotsnake.tic", hash = "e3a453cec0dd3a2e1da98f3f15caac73", id = 3794, filename = "knotsnake.tic"}, 
	{ name = "les dents de sa mere.tic", hash = "8babe6a50bf4cfb739bc6638f4437dba", id = 3785, filename = "les_dents_de_sa_mere.tic"}, 
	{ name = "net.haxe.tic", hash = "961302fe93b054425dee369836825189", id = 3797, filename = "net_haxe.tic"}, 
	{ name = "MINIRALLY.tic", hash = "6a13200f07bb71902ffb01f79a8c2817", id = 3776, filename = "minirally.tic"}, 
	{ name = "Mario Pong.tic", hash = "9bd3500954e944bb77cd1130d7a2f74a", id = 3791, filename = "mario_pong.tic"}, 
	{ name = "wobble effect.tic", hash = "5d0823d09f732d63222b2cc155513515", id = 3782, filename = "wobble_effect.tic"}, 
	{ name = "OniTower.tic", hash = "677b74e9fbc43e4a5dda9e17107a8012", id = 3792, filename = "onitower.tic"}, 
	{ name = "Lunar Harvest.tic", hash = "9f71fd4f0dfaacfb8c536467ed37aeac", id = 3796, filename = "lunar_harvest.tic"}, 
	{ name = "Particle Forge.tic", hash = "e6228f35ea0aec384ed8e0ae48b44cc9", id = 3787, filename = "particle_forge.tic"}, 
	{ name = "In the Hollows.tic", hash = "02c31290a81d3bfcaa9ede5955800307", id = 3784, filename = "in_the_hollows.tic"}, 
	{ name = "Happy Women&#39;s Day!.tic", hash = "6eb6dcb27886bfa9211452d5634cc970", id = 3789, filename = "happy_women_s_day.tic"}, 

}
```

#### Classes
##### Folder 
```{ name = "Foldername" }"```
##### File
```{ name = "Cart display name.tic", hash = "00000000000000000000000000000000", id = 0, filename = "cart_filename.tic"}``` 

(`hash` will be used later)

## Download cart
### Request
```GET /cart/{hash}/{filename}```

### Response
In response you get the *.tic file to load.

## Get cart cover image
### Request
```GET /cart/{hash}/cover.gif```

### Response
In response you get a *.gif image of cover
