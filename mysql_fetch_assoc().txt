// For SubSearch/roaming


Add "if ($var)" boolean check to mysql_fetch_assoc($var) to eliminate warning --->

mysql_fetch_assoc() expects parameter 1 to be resource, boolean given in <path>

Otherwise shows "No Data available" with empty map for IMSIs that actually have roaming data.
This prevents map data to be loaded. Doesn't do much of a harm itself.
