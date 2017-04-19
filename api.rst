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

game_spawn_contract
~~~~~~~~~~~~~~~~~~~

game_spawn_contract()

game_spawn_resume
~~~~~~~~~~~~~~~~~

game_spawn_resume()

Player
------

player_set_win_money
~~~~~~~~~~~~~~~~~~~~

Set the amount of money a player needs to win the level.

.. code-block:: js

	player_set_win_money(playerId, amount)

+------------------------+------------+--------------------+
| Param                  | Type       | Description        |
+========================+============+====================+
| playerId               | Player ID  | 0 - 4              |
+------------------------+------------+--------------------+
| amount                 | Number     | Amount of money.   |
+------------------------+------------+--------------------+

player_set_fail_seconds
~~~~~~~~~~~~~~~~~~~~~~~

Set the duration a player needs to be bankrupt in order to lose the level.

.. code-block:: js

	player_set_fail_seconds(playerId, amount)

+------------------------+------------+--------------------+
| Param                  | Type       | Description        |
+========================+============+====================+
| playerId               | Player ID  | 0 - 4              |
+------------------------+------------+--------------------+
| amount                 | Number     | Time in seconds.   |
+------------------------+------------+--------------------+

player_set_population_cap
~~~~~~~~~~~~~~~~~~~~~~~~~

player_set_population_cap(interns, employees)

player_set_rep
~~~~~~~~~~~~~~

Set a players reputation with a company.

player_set_rep(playerId, companyId, amount)

player_move_camera
~~~~~~~~~~~~~~~~~~

player_move_camera(playerId, targetPosX, targetPosY, targetPosZ, zoom, speed)

Items
-----

item_spawn
~~~~~~~~~~

Spawn an item.
Returns entity ID of spawned item.

Item_spawn(playerId, assetName, posX, posY, rot)

item_set_available
~~~~~~~~~~~~~~~~~~

Makes an item available/unavailable for a player to place.

item_set_available(playerId, assetName, isAvailable)

item_spawn_notify
~~~~~~~~~~~~~~~~~

Spawn a notification for the player that an item is available.

item_spawn_notify(playerId, assetName)

item_spawn_blueprint
~~~~~~~~~~~~~~~~~~~~

Spawn a blueprint.

item_spawn_blueprint(playerId, assetName, posX, posY, rot)

item_set_locked
~~~~~~~~~~~~~~~

Set the locked state of a door.

item_set_locked(doorId, isLocked)

doorId (number): entity ID of the door.
isLocked (boolean): true = locked, false = unlocked.

Units
-----

unit_spawn
~~~~~~~~~~

Spawns a unit.

unit_spawn(playerId, posX, posY, rot, tier, level)

Returns entity ID of spawned unit.

unit_set_speech
~~~~~~~~~~~~~~~

unit_set_speech(unitId, text)

unit_set_stamina
~~~~~~~~~~~~~~~~

unit_set_stamina(unitId, amount)

unit_get_alive
~~~~~~~~~~~~~~

unit_get_alive(unitId)

AI
--

ai_set_active
~~~~~~~~~~~~~

ai_set_active(playerId, isActive)

Cinematics
----------

Audio
-----

audio_play_music
~~~~~~~~~~~~~~~~

audio_play_music(playerId, musicId)

audio_play_sound
~~~~~~~~~~~~~~~~

audio_play_sound(playerId, soundId)

Localization
------------

locale_get_locale
~~~~~~~~~~~~~~~~~

locale_get_locale()

locale_get_string
~~~~~~~~~~~~~~~~~

locale_get_string(stringId)

Waits
-----

A wait function will pause script execution until a certain condition has been met.

.. code-block:: js

    function on_start()
    {
	    wait_tick(50);
    }

wait_time
~~~~~~~~~

wait_time(ticks)

Triggers
--------

A trigger function will schedule a function to execute when a certain condition has been met. All trigger functions return a 'Trigger ID' that can be used to cancel the trigger.

trigger_cancel
~~~~~~~~~~~~~~

trigger_cancel(triggerId)

trigger_tick
~~~~~~~~~~~~

trigger_tick(tick, callback)

trigger_unit_dead
~~~~~~~~~~~~~~~~~

trigger_unit_dead(unitId, callback)