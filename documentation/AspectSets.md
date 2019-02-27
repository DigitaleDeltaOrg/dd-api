# Aspect sets
Often the measurements produced by a sensor are processed into a set of time series with variables that have been derived from the original series of measurements.  For example, for a certain chosen interval length the following related values of a measurement could be determined per interval:

* average
* minimum
* maximum
* standard deviation
* ...

Another example of related values is the set of indicators that describe a wave-field measurement. Per twenty-minute interval, various values are determined, e.g. Hmax, H1/50, H1/10, H1/3, GGH, et cetera.

The DD-API offers a mechanism to provide these related time series in one response, by grouping them in a so called AspectSet. An end point `/aspectsets` specifies which sets are known to the providing system. Each set is specified by its name and the ‘aspects’, i.e. the  names of the variables of the related time series. See the response documentation of the `/aspectsets` end point for an example of an AspectSet.
When asking for a timeseries, the name of the requested AspectSet can be provided as a filter in the `/timeseries` end point:
`/timeseries?locationName=LOC_A&quantity=WaterLevel&aspectset=AverMinMax`  
See the response documentation of the '/timeseries' end point for an example of the way the values of the aspects are returned in a time series.

