Game.Win('Third-party');
if(Core blaster === undefined) var CoreBlaster = {};
if(typeof CCSE == 'undefined') Game.LoadMod('https://klattmose.github.io/CookieClicker/' + (0 ? 'Beta/' : '') + 'CCSE.js');
CoreBlaster.name = 'Core Blaster';
CoreBlaster.version = '1';
CoreBlaster.GameVersion = '2.031';

CoreBlaster.launch = function(){
	CoreBlaster.init = function(){
		var iconsURL = 'https://klattmose.github.io/CookieClicker/img/customIcons.png';
		
		CCSE.NewBuilding('Core Blaster',
			'black hole inverter|black hole inverters|blasted|[X]% more electricity|[X]% more electricity',
			'Blasts cookie electricity at anything to transform it into cookies.',
			1,
			1,
			{
				base:'https://klattmose.github.io/CookieClicker/img/blackholeinverter',
				xV:8,
				yV:32,
				w:128,
				rows:1,
				x:0,
				y:0,
				customBuildingPic:'https://klattmose.github.io/CookieClicker/img/customBuildings.png',
				customIconsPic:iconsURL
			},
			"doesn't matter what you put here",
			function(me){
				var mult = 1;
				mult *= Game.GetTieredCpsMult(me);
				mult *= Game.magicCpS(me.name);
				return me.baseCps * mult;
			},
			function(){
				Game.UnlockTiered(this);
				if(this.amount >= Game.SpecialGrandmaUnlock && Game.Objects['Grandma'].amount > 0) Game.Unlock(this.grandma.name);
			},
			{
				name:'Hypnodrone',
				desc:'Autonomous aerial brand ambassadors to "encourage" more sales!',
				icon:1
			},
			['Kugelblitz', 'Spaghettification']
		);
		
		Game.Objects['Core Blaster'].displayName='<span style="font-size:80%;position:relative;bottom:4px;">Black hole inverter</span>'; // Shrink the name since it's so large
		
		
		// Upgrades
		var last; var i = 0; var order = CoreBlaster.getTieredUpgradeOrder();
		last = Game.TieredUpgrade('Blacker holes', 'Black hole inverters are <b>twice</b> as efficient.<q>Bigger and blacker.</q>', 'Black hole inverter', 1); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Blackest holes', 'Black hole inverters are <b>twice</b> as efficient.<q>The biggest and blackest.</q>', 'Black hole inverter', 2); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Vantablack holes', 'Black hole inverters are <b>twice</b> as efficient.<q>The universe doesn\'t care about some idiot\'s copyright.</q>', 'Black hole inverter', 3); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('African-American holes', 'Black hole inverters are <b>twice</b> as efficient.<q>Some people take political correctness a little too far.</q>', 'Black hole inverter', 4); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Event Horizon Comics', 'Black hole inverters are <b>twice</b> as efficient.<q>dot com</q>', 'Black hole inverter', 5); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Large Hadron Collider', 'Black hole inverters are <b>twice</b> as efficient.<q>Smashing things together has never been so well funded!</q>', 'Black hole inverter', 6); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Superconducting Super Collider', 'Black hole inverters are <b>twice</b> as efficient.<q>In the land of what might have been.</q>', 'Black hole inverter', 7); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Hawking radiators', 'Black hole inverters are <b>twice</b> as efficient.<q>14 March 2018.</q>', 'Black hole inverter', 8); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Micro black holes', 'Black hole inverters are <b>twice</b> as efficient.<q>Fun sized</q>', 'Black hole inverter', 9); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Accretion disco', 'Black hole inverters are <b>twice</b> as efficient.<q>Everybody dance now!</q>', 'Black hole inverter', 10); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Gravitational waves', 'Black hole inverters are <b>twice</b> as efficient.<q>What\'s better that one black hole? Two of them put together!</q>', 'Black hole inverter', 11); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('White holes', 'Black hole inverters are <b>twice</b> as efficient.<q>Don\'t tan well, huh?</q>', 'Black hole inverter', 12); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredUpgrade('Holes', 'Black hole inverters are <b>twice</b> as efficient.<q>It\'s also a book</q>', 'Black hole inverter', 13); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		
		order = CoreBlaster.getGrandmaUpgradeOrder();
		last = Game.GrandmaSynergy('Heavy grandmas', 'A dense grandma to accrete more cookies.', 'Black hole inverter'); last.order = order;
		
		order = CoreBlaster.getSynergyUpgradeOrder();
		last = Game.SynergyUpgrade('Daring pilots', "<q>You've never heard of the Millennium Falcon? It's the ship that made the Kessel Run in less than twelve parsecs.</q>", 'Black hole inverter', 'Shipment', 'synergy1'); last.icon[2] = iconsURL; last.order = order;
		last = Game.SynergyUpgrade('General relativity', '<q>Space is time. Time is space</q>', 'Black hole inverter', 'Time machine', 'synergy2'); last.icon[2] = iconsURL; last.order = order + 0.01;
		
		
		// Achievements
		order = CoreBlaster.getAchievementOrder(); i = 0;
		last = Game.TieredAchievement('Single singularity', 'Have <b>1</b> black hole inverter.', 'Core Blaster', 1); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Penrose diagram', 'Have <b>50</b> black hole inverters.', 'Core Blaster', 2); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Schwarzschild', 'Have <b>100</b> black hole inverters.', 'Core Blaster', 3); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Holes in holes', 'Have <b>150</b> black hole inverters.', 'Core Blaster', 4); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('No-hair theorem', 'Have <b>200</b> black hole inverters.', 'Core Blaster', 5); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Photon sphere', 'Have <b>250</b> black hole inverters.', 'Core Blaster', 6); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Information paradox', 'Have <b>300</b> black hole inverters.', 'Core Blaster', 7); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Gravitaional lensing', 'Have <b>350</b> black hole inverters.', 'Core Blaster', 8); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Galactic nuclei', 'Have <b>400</b> black hole inverters.', 'Core Blaster', 9); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Sagittarius A*', 'Have <b>450</b> black hole inverters.', 'Core Blaster', 10); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Hey now, you\'re a dead star', 'Have <b>500</b> black hole inverters.', 'Core Blaster', 11); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Incredibly dense', 'Have <b>550</b> black hole inverters.', 'Core Blaster', 12); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.TieredAchievement('Infinitely dense', 'Have <b>600</b> black hole inverters.', 'Core Blaster', 13); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		
		last = Game.ProductionAchievement('Relativistic jets', 'Core Blaster', 1); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.ProductionAchievement('Primordial black holes', 'Core Blaster', 2); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		last = Game.ProductionAchievement('Naked singularity', 'Core Blaster', 3); last.icon[2] = iconsURL; last.order = order + i / 100; i++;
		
		last = CCSE.NewAchievement('M87', 'Reach level <b>10</b> black hole inverters.', [1, 26, iconsURL]); 
			Game.Objects['Core Blaster'].levelAchiev10 = last; last.order = order + i / 100; i++;
		
		
		
		Game.customStatsMenu.push(function(){
			CCSE.AppendStatsVersionNumber(BlackholeInverter.name, BlackholeInverter.version);
		});
		
		// Finish up
		BlackholeInverter.isLoaded = 1;
		if(BlackholeInverter.postloadHooks){
			for(var i = 0; i < BlackholeInverter.postloadHooks.length; ++i) BlackholeInverter.postloadHooks[i]();
		}
		
		if (Game.prefs.popups) Game.Popup(BlackholeInverter.name + ' loaded!');
		else Game.Notify(BlackholeInverter.name + ' loaded!', '', '', 1, 1);
	}
	
	
	BlackholeInverter.getTieredUpgradeOrder = function(){
		function isNumber(n) {
			return !isNaN(parseFloat(n)) && isFinite(n);
		}
		
		var res = 0;
		for(var i = 0; i < Game.ObjectsN; i++){
			var me = Game.ObjectsById[i];
			for(var ii in me.tieredUpgrades){
				if(isNumber(ii)) res = Math.max(me.tieredUpgrades[ii].order, res);
			}
		}
		
		return res + 0.01;
	}
	
	BlackholeInverter.getGrandmaUpgradeOrder = function(){
		var res = 0;
		for(var i in Game.GrandmaSynergies){
			res = Math.max(Game.Upgrades[Game.GrandmaSynergies[i]].order, res);
		}
		
		return res + 0.01;
	}
	
	BlackholeInverter.getSynergyUpgradeOrder = function(){
		var res = 0;
		for(var i = 0; i < Game.ObjectsN; i++){
			var me = Game.ObjectsById[i];
			for(var ii in me.synergies){
				res = Math.max(me.synergies[ii].order, res);
			}
		}
		
		return res + 0.01;
	}
	
	BlackholeInverter.getAchievementOrder = function(){
		var res = 0;
		for(var i = 0; i < Game.ObjectsN-1; i++){
			var me = Game.ObjectsById[i];
			
			for(var ii in me.tieredAchievs){
				res = Math.max(me.tieredAchievs[ii].order, res);
			}
			
			for(var ii in me.productionAchievs){
				res = Math.max(me.productionAchievs[ii].achiev.order, res);
			}
			
			if(me.levelAchiev10) res = Math.max(me.levelAchiev10.order, res);
		}
		
		return res + 0.01;
	}
	
	
	if(CCSE.ConfirmGameVersion(BlackholeInverter.name, BlackholeInverter.version, BlackholeInverter.GameVersion)) BlackholeInverter.init();
}


if(!BlackholeInverter.isLoaded){
	if(CCSE && CCSE.isLoaded){
		BlackholeInverter.launch();
	}
	else{
		if(!CCSE) var CCSE = {};
		if(!CCSE.postLoadHooks) CCSE.postLoadHooks = [];
		CCSE.postLoadHooks.push(BlackholeInverter.launch);
	}
}
