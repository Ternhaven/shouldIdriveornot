# drive-or-bike
Information about gasoline and electricity prices in Sweden

## How to use

### Quick Use - script.py

Simply call `python script.py` to quickly scrape the websites and create a plot, *circleplot.png*.

### notebook.ipynb

The two scraper functions, `electricity_price` and `gasoline_price` each return a number: the current price of electricity (Swedish Krona [SEK] per kilowatt-hour [kWh]) and gasoline (SEK/Liter), respectively.

If we have that
```
elec_price = electricity_price()
gas_price = gasoline_price()
```

The total cost (in SEK) of a trip of `x` kilometers can then be calculated:
```
electricity_cost_sek(x, elec_price)  # (For an ebike)
gasoline_cost_sek(x, gas_price)   # (For a car)
```

The function `electricity_cost_sek` assumes a default value of 100 kilometers per kWh efficiency; likewise, `gasoline_cost_sek` assumes a default value of 9.4 kilometers per liter efficiency. Each of these functions can take a third argument if you would like to set either efficiency to a different value, i.e. `electricity_cost_sek(x, elec_price, 80.0)`.
