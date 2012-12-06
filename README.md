# Dates and Times for Julia

 The types and functions in this class store and manipulate representations of dates and times
 Instances are stored internally as a Julian Date (jd), which is a representation of dates counting linearly
 in days since midnight localtime on January 1, 4713 BCE. The original Julian Day Number, counting in days
 since noon GMT, is refered to as the astronomical julian date (ajd) within this code base.

 Only minimal timezone support currently exists. DateTime objects keep track of timezones supplied, and use timezones
 in difference calculations. However, no timezone conversion functionality is provided. DST is also not
 considered by this code. Both these items are cosidered to be the responsibility of the calling code.

 ##Examples

 ```julia
load("SimpleDate/src/SimpleDate")
using SimpleDate

d = datetime(2012, 4, 24, 13,10,5) 
@assert hour(d) == 13
@assert minute(d)==10
@assert second(d) == 5
@assert mday(d) == 24
@assert month(d) == 4
@assert year(d) == 2012

d = date(2012,2,1)
@assert year(d) == 2012
@assert month(d) == 2
@assert mday(d) == 1
@assert wday(d) == 4 #Wednesday

 ```

## EXPERIMENTAL!! USE AT OWN RISK.
