TestFlight-Stock (TestFlight-Configs-Revived)
============
Forum: https://forum.kerbalspaceprogram.com/index.php?/topic/209303-112x-testflight-stock-testflight-configs-revived-v030-beta-2-years-5-months-a-week-and-two-days/

Original repository: https://github.com/Starstrider42/TestFlight-Configs

This is a config pack originally created by Starstrider42, however development stopped at KSP 1.8/1.9 with the latest version released more than two years ago. Because of that, I've decided to adopt and modify it, aiming to include support for stock and (hopefully) all existing part mods.

Since Github doesn't allow issues in forked repositories, please report any bug related to the mod here: https://forum.kerbalspaceprogram.com/index.php?/topic/211274-testflight-stock-bug-tracker/

Modifications: 
-------
* Engine reliability and ignition chance now depends on it's position on the tech tree and features of higher performance and quality (TWR, engine efficiency, reusability, cost,...)
* Prototype/experimental engines using brand-new engine cycle and propellant technologies, whether stated in the description itself, through logical indications derived from engine performance (for example, hydrolox engines usually have a vacuum specific impulse of over 400 isp) or from actual designs their real-life analogs, will have lower reliability than the older engines utilizing tested and perfected engineering.
* Tech transfers can only be done with engines within the same family, engineering principles and propellant types. The amount of transfers increase if there's more similarities.
* Heat shields are no longer supported.

Notes:
-------
* TestFlight-Stock, while being "alternative", gives a more individualized and unique system for TF than the official default configs. 
* Contrary to popular belief, TestFlight works perfectly with Kerbalism and ~~OhScrap~~ (currently working with Zer0Kerbal to solve this). Do not afraid to install TF and TF-Stock if you have those mods installed (SRB failures handling will use TF-Stock and not OhScrap).

While Starstrider's contents remains under the MIT license, my modifications are released under the GNU General Public License v3.0. The license can be found in the repository's LICENSE file as usual, or at the website here: https://opensource.org/licenses/gpl-3.0.html

From Starstrider42:
-------

"These are alternative configs created for [TestFlight 1.8](https://github.com/KSP-RO/TestFlight). Currently, only engines and heat shields are supported; I will be adding configs for other stock parts and mods I play with as time permits.

The configs are inspired by the ones that ship with Realism Overhaul, but are designed to be a bit more forgiving at the expense of realism. I've tried to follow hints from the part descriptions. For example, the RT-series boosters and the 3.75 m Kerbodyne engines are a bit prone to exploding, and the Kerbodyne engines start out very unreliable.

Parts can inherit engineering experience from other parts, but only from the same manufacturer. The amount of data transferred is normally 50% for parts in the same series, but can vary from 75% (nearly identical components) to 25% (not really related, but the company must have learned general principles from the previous model).

Engines
-------

* All engines follow the Realism Overhaul failure curve: they are up to ten times more likely to fail in the first five seconds after ignition, have their nominal failure rate up until their rated burn time, then grow much more likely to fail after that. Burn time is tracked in a way that does not reset if you shut down and quickly restart an engine.
* Reusable engines will "forget" previous burns when shut down for long enough. This allows multiple burns with no penalty for cumulative burn time, while ensuring a failure spike at the start of each burn.
* Engines that have ignition failures are less likely to ignite above a dynamic pressure of 5 kPa (90 m/s at Kerbin sea level), with the ignition chance falling to half its normal value at 27 kPa (210 m/s at sea level). Engines designed for air starts, like the Launch Escape System, have higher pressure thresholds.
* All gimbaled engines have a common set of gimbal failures: gimbal lock (57%), gimbal speed loss (29%), and a permanent gimbal offset (14%).
* Bipropellant rockets have rated burn times of 2-5 minutes, depending on whether they're intended for launch or deep-space maneuvers. They typically have 45-99.5% reliability (chance of *not* failing in one RBT), and may suffer a wide range of failures (see table below). They also have a chance of failure every time they are ignited. For launch engines this is typically 0.5-25%; for deep-space engines, it's 0.1-15%.
* Monopropellant rockets have 90-99.8% reliability, and are ~~immune~~ to ignition failures. Otherwise, they behave like bipropellant rockets.
* Solid-fuel rockets have rated burn times corresponding to 50-60% thrust. They have 70-99.5% reliability and are immune to most failure modes, but have a higher chance of exploding when they do fail. They rarely suffer ignition failures (0.05-10% of the time).
* Jet engines have rated burn times of hours to allow for extended flights. They are initially only 50% reliable (i.e., even a short flight can see a failure), but become >99% reliable when fully developed. Jet engines have similar failure modes to liquid-fueled rockets, but ~~always~~ at most times ignite and are less likely to overheat.
* The J-404 and RAPIER currently do not have TestFlight support, because TestFlight does not support stock multi-mode engines.
* Nuclear engines and other thermal rockets have rated burn times of 10-15 minutes to allow low-thrust interplanetary burns. Like jet engines, they have low initial reliability (70%) to compensate for their long burn time. They have similar failure modes to monopropellant rockets, but are even more reliable when mature (99%).
* Ion thrusters typically have rated burn times of 20-30 minutes and reliabilities of 85-99.5%. They cannot explode or overheat, but are more likely than other kinds of thrusters to lose specific impulse.
* Electromagnetic thrusters typically have rated burn times of 10-20 minutes and reliabilities of 85-99.8%. They cannot explode or overheat.
* Electrothermal thrusters typically have rated burn times of 10-20 minutes and reliabilities of 84-99.8%. They have similar failure modes to electromagnetic thrusters, but can also develop cooling problems.

Below is the spreadsheet displaying various failure modes and their probabilities for respective engine types. Note that the numbers are calculated under the assumption that the engine can gimbal, and integrated fuel tanks is not accounted for. Start-up reliability is directly calculated using ignitionReliabilityStart/End.

| Engine type     | Shutdown | Low I<sub>sp</sub> | Low Thrust | Overheat | Explode | Vector Glitch | Sluggish Vector |
| --------------- | -------- | ------------------ | ---------- | -------- | ------- | ------------- | --------------- |
| Liquid-Fuel     | 43%      | 22%                | 11%        | 5%       | 3%      | 5%            | 11%             |
| Solid-Fuel      |          | 53%                |            |          | 7%      | 13%           | 27%             |
| Jet Turbine     | 44%      | 22%                | 11%        | 3%       | 3%      | 6%            | 11%             |
| Ramjet          | 47%      | 23%                | 12%        |          |         | 6%            | 12%             |
| Turboramjet     | 46%      | 23%                | 11%        |          | 3%      | 6%            | 11%             |
| Thermal Ramjet  | 44%      | 22%                | 11%        |          | 6%      | 6%            | 11%             |
| Thermal Rocket  | 43%      | 22%                | 11%        | 5%       | 3%      | 5%            | 11%             |
| Cold Gas        | 46%      | 23%                | 11%        |          | 3%      | 6%            | 11%             |
| Electrostatic   | 23%      | 47%                | 12%        |          |         | 6%            | 12%             |
| Electromagnetic | 31%      | 31%                | 15%        |          |         | 8%            | 15%             |
| Electrothermal  | 29%      | 29%                | 14%        | 7%       |         | 7%            | 14%             |
| Electric Motors | 53%      | 3%                 | 13%        | 7%       | 3%      | 7%            | 13%             |

Heat Shields
------------

* Ablative heat shields have a constant failure rate while the shield is ablating. The rate does not depend on how long the shield has been hot or on the ablation rate.
* Heat shields are typically 45-99.5% reliable over a 6-minute re-entry.
* Inflatable heat shields like the stock 10-meter do not currently have any failure modes.

License
------------
These configs are released under the MIT License. A copy of the license can be found in the file `LICENSE` in the mod directory, or online at http://opensource.org/licenses/MIT."
