API
===

Common Parameters
-----------------

- playerId (number): ID of player, 0 to 4. (4 is neutral player - no base)
- unitId (number): Entity ID of a unit.
- itemId (number): Entity ID of an item.
- posX (number): Position value.
- posY (number): Position value.
- posZ (number): Position value.
- rot (number): Rotation value in degrees. (Sometimes 0-3 representing 90° intervals)
- assetName (string): Name of an asset.

Game
----

game_set_win_money
~~~~~~~~~~~~~~~~~~

Set the amount of money a player needs to win the level.

.. code-block:: js

	game_set_win_money(playerId, amount)

+------------------------+------------+--------------------+
| Param                  | Type       | Description        |
+========================+============+====================+
| playerId               | Player ID  | 0 - 4              |
+------------------------+------------+--------------------+
| amount                 | Number     | Amount of money.   |
+------------------------+------------+--------------------+

game_set_fail_seconds
~~~~~~~~~~~~~~~~~~~~~

Set the duration a player needs to be bankrupt in order to lose the level.

.. code-block:: js

	game_set_fail_seconds(playerId, amount)

+------------------------+------------+--------------------+
| Param                  | Type       | Description        |
+========================+============+====================+
| playerId               | Player ID  | 0 - 4              |
+------------------------+------------+--------------------+
| amount                 | Number     | Time in seconds.   |
+------------------------+------------+--------------------+

game_set_fail_seconds(amount)
game_set_population_cap(amount)
game_set_intern_cap(amount)

game_spawn_contract()
game_spawn_resume()


Player
------

player_set_rep(playerId, companyId, amount)
Set a players reputation with a company.

player_move_camera(playerId, targetPosX, targetPosY, targetPosZ, zoom, speed)

Items
-----

Item_spawn(playerId, assetName, posX, posY, rot)
Spawn an item.
Returns entity ID of spawned item.

item_set_available(playerId, assetName, isAvailable)
Makes an item available/unavailable for a player to place.

item_spawn_notify(playerId, assetName)
Spawn a notification for the player that an item is available.

item_spawn_blueprint(playerId, assetName, posX, posY, rot)
Spawn a blueprint 

item_set_locked(doorId, isLocked)
Set the locked state of a door.
doorId (number): entity ID of the door.
isLocked (boolean): true = locked, false = unlocked.


Units
-----

unit_spawn(playerId, posX, posY, rot, tier, level)
Spawns a unit.
Returns entity ID of spawned unit.

unit_set_speech(unitId, text)
unit_set_stamina(unitId, amount)
unit_get_alive(unitId)


AI
--

ai_set_active(playerId, isActive)

Cinematics
----------

Audio
-----

audio_play_music(playerId, musicId)
audio_play_sound(playerId, soundId)

Localization
------------

locale_get_locale()
locale_get_string(stringId)

Waits
-----

A wait function will pause script execution until a certain condition has been met.

.. code-block:: js

    function on_start()
    {
	    wait_tick(50);
    }

wait_time(ticks)

Triggers
--------

A trigger function will schedule a function to execute when a certain condition has been met. All trigger functions return a 'Trigger ID' that can be used to cancel the trigger.


trigger_cancel(triggerId)
trigger_tick(tick, callback)
trigger_unit_dead(unitId, callback)