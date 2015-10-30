# Garki

## Dcell enigma

- VectorHabitat.cpp:            
  `case VectorHabitatType::TEMPORARY_RAINFALL:
VectorHabitat.cpp:                LOG_DEBUG_F("Habitat type = TEMPORARY_RAINFALL, Max larval capacity = %f\n", m_max_larval_capacity);`

  `case VectorHabitatType::TEMPORARY_RAINFALL:
m_current_larval_capacity += (float)( localWeather->accumulated_rainfall() * m_max_larval_capacity * params()->lloffset * params()->lloffset - m_current_larval_capacity * exp(LARVAL_HABITAT_FACTOR1 / (localWeather->airtemperature() + CELSIUS_TO_KELVIN)) * LARVAL_HABITAT_FACTOR2 * params()->tempHabitatDecayScalar * sqrt(LARVAL_HABITA    T_FACTOR3 / (localWeather->airtemperature() + CELSIUS_TO_KELVIN)) * (1.0f - localWeather->humidity()) * dt );`

- Node.cpp:            
  `cellarea = (float) (EARTH_RADIUS_KM * EARTH_RADIUS_KM * (cos(lat_rad1) - cos(lat_rad2)) * params()->lloffset * 2.0 * (PI / 180.0));`
  `Node.cpp:        if (params()->lloffset > 0) // check to make sure area will be nonzero
Node.cpp:            float lat_rad1 = (float) (( 90.0 - lat_deg - params()->lloffset ) * PI / 180.0);
Node.cpp:            float lat_rad2 = (float) (( 90.0 - lat_deg + params()->lloffset ) * PI / 180.0);
Node.cpp:            cellarea = (float) (EARTH_RADIUS_KM * EARTH_RADIUS_KM * (cos(lat_rad1) - cos(lat_rad2)) * params()->lloffset * 2.0 * (PI / 180.0));`


```
demographics.json:        "IdReference": "Gridded world grump2.5arcmin",
humidity.bin.json:          "IdReference": "Gridded world grump2.5arcmin",
rainfall.bin.json:          "IdReference": "Gridded world grump2.5arcmin",
temperature.bin.json:          "IdReference": "Gridded world grump2.5arcmin",
```

Thus llofset= .5* node_grid_size
464 meters  from: [.25 arc min = 15 arc sec](http://www.wolframalpha.com/input/?i=.25+arc+minutes)
## Habitat types

VectorHabitat.cpp:            case VectorHabitatType::CONSTANT:
m_current_larval_capacity = m_max_larval_capacity * params()->lloffset * params()->lloffset;


VectorHabitat.cpp:            case VectorHabitatType::WATER_VEGETATION:
VectorHabitat.cpp:            case VectorHabitatType::HUMAN_POPULATION:
VectorHabitat.cpp:            case VectorHabitatType::BRACKISH_SWAMP:
