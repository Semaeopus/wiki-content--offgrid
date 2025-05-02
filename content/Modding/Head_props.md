# Head_props

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Head_props*

*Scraped on: 2025-05-02 18:40:19*

## Introduction
When setting up a character in Mission Script it's possible to define their head props, like hair, hats, glasses and earpieces. There is no limit to the number of props used in a character (apart from how well all the props fit together). If nothing is defined then the character will use whatever default props the character prefab might have.
## Script Example
```
characters = {
        guard1 = {
            displayName = "Marcus Fordham",
            internalName = "guard1",
            prefab = "Masculine_Med_Vest_Enemy",
            headProps =
            {
                 "F_Lrg_Earpiece_01", "M_Lrg_Hair-Long-Ponytail-Fringe_01", "F_Med_Glasses-01"
            },
        }
```
## Hair Prop List
| Prefab Name | Image(s) | Note |
| --- | --- | --- |
| * F_Lrg_Hair-Long-Fringe_01* F_Med_Hair-Long-Fringe_01* M_Lrg_Hair-Long-Fringe_01* M_Med_Hair-Long-Fringe_01 |  | Long hair with a fringe |
| * F_Lrg_Hair-Long-Ponytail-Fringe_01* F_Med_Hair-Long-Ponytail-Fringe_01* M_Lrg_Hair-Long-Ponytail-Fringe_01* M_Med_Hair-Long-Ponytail-Fringe_01 |  | Long hair with a ponytail |
| * F_Lrg_Hair-Long-Wavey_01* F_Med_Hair-Long-Wavey_01* M_Lrg_Hair-Long-Wavey_01* M_Med_Hair-Long-Wavey_01 |  | Wavey long hair |
| * F_Lrg_Hair-Long-Wavey_02* F_Med_Hair-Long-Wavey_02* M_Lrg_Hair-Long-Wavey_02* M_Med_Hair-Long-Wavey_02 |  | Wavey long hair |
| * F_Lrg_Hair-Short-Buzz_01* F_Med_Hair-Short-Buzz_01* M_Lrg_Hair-Short-Buzz_01* M_Med_Hair-Short-Buzz_01 |  | Short buzz cut hair |
| * F_Lrg_Hair-Short-Curly-Clip_01* F_Med_Hair-Short-Curly-Clip_01* M_Lrg_Hair-Short-Curly-Clip_01* M_Med_Hair-Short-Curly-Clip_01 |  | Curly short hair |
| * F_Lrg_Hair-Short-Pointy_01* F_Med_Hair-Short-Pointy_01* M_Lrg_Hair-Short-Pointy_01* M_Med_Hair-Short-Pointy_01 |  | Pointy short hair |
| * F_Lrg_Hair-Short-SideFringe_01* F_Med_Hair-Short-SideFringe_01* M_Lrg_Hair-Short-SideFringe_01* M_Med_Hair-Short-SideFringe_01 |  | Short hair with a side fringe |
| * F_Lrg_Hair-Short-SideFringe_02* F_Med_Hair-Short-SideFringe_02* M_Lrg_Hair-Short-SideFringe_02* M_Med_Hair-Short-SideFringe_02 |  | Short hair with a side fringe |
| * F_Lrg_Hair-Big-Curly_01* F_Med_Hair-Big-Curly_01* M_Lrg_Hair-Big-Curly_01* M_Med_Hair-Big-Curly_01 |  | Big curly hair |
| * F_Lrg_Hair-Afro_01* F_Med_Hair-Afro_01* M_Lrg_Hair-Afro_01* M_Med_Hair-Afro_01 |  | Afro hair |
| * F_Lrg_Hair-Pompadour_01* F_Med_Hair-Pompadour_01* M_Lrg_Hair-Pompadour_01* M_Med_Hair-Pompadour_01 |  | Pompadour hair style |
| * F_Lrg_Hair-Punk_01* F_Med_Hair-Punk_01* M_Lrg_Hair-Punk_01* M_Med_Hair-Punk_01 |  | Punk Spiky Hair / Biker |
| * F_Lrg_Hair-Short-Buzz_01* F_Med_Hair-Short-Buzz_01* M_Lrg_Hair-Short-Buzz_01* M_Med_Hair-Short-Buzz_01 |  | Short Buzz cut |
| * F_Lrg_Hair-Balding_01* F_Med_Hair-Balding_01* M_Lrg_Hair-Balding_01* M_Med_Hair-Balding_01 |  | Balding hairstyle |
## Facial Hair Prop List
| Prefab Name | Image(s) | Note |
| --- | --- | --- |
| * F_Lrg_Beard-Big_01* F_Med_Beard-Big_01* M_Lrg_Beard-Big_01* M_Med_Beard-Big_01 |  | A big beard |
| * F_Lrg_Beard-Goatee_01* F_Med_Beard-Goatee_01* M_Lrg_Beard-Goatee_01* M_Med_Beard-Goatee_01 |  | A goatee face prop. |
| * F_Lrg_Beard-Moustache_01* F_Med_Beard-Moustache_01* M_Lrg_Beard-Moustache_01* M_Med_Beard-Moustache_01 |  | A moustache face prop. |
| * F_Lrg_Beard-Moustache_02* F_Med_Beard-Moustache_02* M_Lrg_Beard-Moustache_02* M_Med_Beard-Moustache_02 |  | A moustache face prop. |
| * F_Lrg_Beard-Moustache_03* F_Med_Beard-Moustache_03* M_Lrg_Beard-Moustache_03* M_Med_Beard-Moustache_03 |  | A moustache face prop. |
| * F_Lrg_Beard-Muttonchops_01* F_Med_Beard-Muttonchops_01* M_Lrg_Beard-Muttonchops_01* M_Med_Beard-Muttonchops_01 |  | Muttonchops facial hair. |
## Hats Prop List
| Prefab Name | Image(s) | Note |
| --- | --- | --- |
| * F_Lrg_Hat-Beanie_01* F_Med_Hat-Beanie_01* M_Lrg_Hat-Beanie_01* M_Med_Hat-Beanie_01 |  | A beanie hat with long ears |
| * F_Lrg_Hat-Beanie_02* F_Med_Hat-Beanie_02* M_Lrg_Hat-Beanie_02* M_Med_Hat-Beanie_02 |  | A beanie hat with long ears |
| * F_Lrg_Hat-Cap_01* F_Med_Hat-Cap_01* M_Lrg_Hat-Cap_01* M_Med_Hat-Cap_01 |  | A cool cap |
| * F_Lrg_Hat-HardHat_01* F_Med_Hat-HardHat_01* M_Lrg_Hat-HardHat_01* M_Med_Hat-HardHat_01 |  | A construction hard hat |
| * F_Lrg_Hat-Cowboy_01* F_Med_Hat-Cowboy_01* M_Lrg_Hat-Cowboy_01* M_Med_Hat-Cowboy_01 |  | A Cowboy hat |
| * F_Lrg_Hat-Headband_01* F_Med_Hat-Headband_01* M_Lrg_Hat-Headband_01* M_Med_Hat-Headband_01 |  | A headband |
| * F_Lrg_Hat-Policeman_01* F_Med_Hat-Policeman_01* M_Lrg_Hat-Policeman_01* M_Med_Hat-Policeman_01 |  | A policeman hat |
| * F_Lrg_Hat-Sunvisor_01* F_Med_Hat-Sunvisor_01* M_Lrg_Hat-Sunvisor_01* M_Med_Hat-Sunvisor_01 |  | Sun visor |
| * F_Lrg_Hat-Swat-Helmet_01* F_Med_Hat-Swat-Helmet_01* M_Lrg_Hat-Swat-Helmet_01* M_Med_Hat-Swat-Helmet_01 |  | A SWAT helmet |
| * F_Lrg_Hat-Propeller-Cap_01* F_Med_Hat-Propeller-Cap_01* M_Lrg_Hat-Propeller-Cap_01* M_Med_Hat-Propeller-Cap_01 |  | A propeller hat |
## Glasses Prop List
| Prefab Name | Image(s) | Note |
| --- | --- | --- |
| * F_Lrg_Glasses-Smart-Frame_01* F_Med_Glasses-Smart-Frame_01* M_Lrg_Glasses-Smart-Frame_01* M_Med_Glasses-Smart-Frame_01 |  | Smart tech glasses |
| * F_Lrg_Glasses-Aviators_01* F_Med_Glasses-Aviators_01* M_Lrg_Glasses-Aviators_01* M_Med_Glasses-Aviators_01 |  | Tinted sunglasses |
| * F_Lrg_Glasses-Swirly_01* F_Med_Glasses-Swirly_01* M_Lrg_Glasses-Swirly_01* M_Med_Glasses-Swirly_01 |  | Swirly hypno glasses |
| * F_Lrg_Glasses-Ski-Goggles_01* F_Med_Glasses-Ski-Goggles_01* M_Lrg_Glasses-Ski-Goggles_01* M_Med_Glasses-Ski-Goggles_01 |  | Ski goggles |
| * F_Lrg_Glasses-Sunglasses-Round_01* F_Med_Glasses-Sunglasses-Round_01* M_Lrg_Glasses-Sunglasses-Round_01* M_Med_Glasses-Sunglasses-Round_01 |  | Round dark sunglasses |
| * F_Lrg_Glasses-Reading_01* F_Med_Glasses-Reading_01* M_Lrg_Glasses-Reading_01* M_Med_Glasses-Reading_01 |  | Reading glasses |
| * F_Lrg_Glasses-Reading_02* F_Med_Glasses-Reading_02* M_Lrg_Glasses-Reading_02* M_Med_Glasses-Reading_02 |  | Reading glasses |
| * F_Lrg_Glasses-Reading_03* F_Med_Glasses-Reading_03* M_Lrg_Glasses-Reading_03* M_Med_Glasses-Reading_03 |  | Reading glasses |
## Miscellaneous Head Prop List
| Prefab Name | Image(s) | Note |
| --- | --- | --- |
| * F_Lrg_Earpiece_01* F_Med_Earpiece_01* M_Lrg_Earpiece_01* M_Med_Earpiece_01 |  | The earpiece for security guards |
| * F_Lrg_AnonMask_01* F_Med_AnonMask_01* M_Lrg_AnonMask_01* M_Med_AnonMask_01 |  | A mask to stay anonymous |
| * F_Lrg_Blindfold_01* F_Med_Blindfold_01* M_Lrg_Blindfold_01* M_Med_Blindfold_01 |  | A blindfold for your character. |