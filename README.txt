# universal_zones_patch
This repository is for the universal zones patch for modders of the game Stellaris post the 4.0 update

Will do updates on Fridays

 universal_zones_patch
 This repository is for the universal zones patch for modders of the game Stellaris post the 4.0 update.

 here's how to use this this repo

 For planet district slots:

slot_energy = {
	inline_script = zones/allowed_zones_energy
	inline_script = zones/*Your Allowed Zone Here*     <---- Copy this line and add it to the desired planet district slot
	unlock = { # planet scope
		custom_tooltip = {
			fail_text = zone_unavailable_tech_power_hub_1
			exists = owner
			owner = {
				has_tech_or_functional_civic = {
					TECH = tech_power_hub_1
				}
			}
		}
	}
}

 Habitat district slots:

 slot_habitat_energy = {
	include = {
		zone_energy
		zone_energy_physics
		zone_habitat_hydroponics
      		*Your Zone Here*                <---- Copy this line and add it to the desired Habitat district slot
unlock = { # planet scope
		custom_tooltip = {
			fail_text = zone_unavailable_tech_power_hub_1
			OR = {
				AND = {
					is_capital = yes
					exists = owner
					owner = {
						is_void_dweller_empire = yes
					}
				}
				AND = {
					exists = owner
					owner = {
						has_tech_or_functional_civic = {
							TECH = tech_power_hub_1
						}
					}
				}
			}
		}
	}
}
