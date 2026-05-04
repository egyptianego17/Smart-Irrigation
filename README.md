# Smart Irrigation

Irrigation controller that talks to Tuya-compatible valves and soil-moisture sensors. Schedules watering, but skips a cycle if the soil is already wet enough or rain is forecast for the next few hours.

Python service on the cloud side, Tuya SDK for the device side. The annoying part was Tuya's auth flow — tokens expire on a clock you don't control, so there's a small refresh layer that wraps every device call.
