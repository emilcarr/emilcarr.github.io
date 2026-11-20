---

layout: post
title: "Picking a Dehumidifier"
byline: "Making sense of the marketing."
by: “Emil Carr-Ross”
date: 2026-11-19 21:18:00 +0000
categories: posts
hidden: true
---

{% include mathjax.html %}

Recently, I had to pick a dehumidifer for my studio ([The Swarf Factory](https://theswarffactory.studio)). I eventually picked the EcoAir DD2 to suit my needs - after sifting through much marketing material and numbers that made no sense. This blog post is intended to help the reader come to their own decision.

## Compressor or Dessicant Dehumidifer?

There are two types of compressors on the market: Dessicant and Compressor types.

Dessicant Dehumidifers work by using a dessicant - a hygroscopic (one which absorbs water) material such as Silica which naturally absorbs water. You will know what this is if you’ve ever looked at those little packets labelled ‘Do Not Eat’ that are thrown into parcels, product packaging and even food. The dessicant is then heated and the water recondenses into the collection tank or drain hose.

Compressor Dehumidifiers work similarly to a fridge - A compressor pump sends a refrigerant through a reverse carnot cycle, creating a cold side and a hot side. Cold air can hold less water, so it condenses out around the cold side and is collected.

As a result, compressor dehumidifiers are more efficient. The only energy input is that to the refrigerant compressor to ‘move’ heat which already exists in the air around.

Dessicant dehumidifers, since they rely on adding heat to the air, are therefore much less efficient. Condensation of water is a latent process - meaning it releases energy - so you actually get more heat out than energy you put in, but not enough to outperform the efficiency of a compressor type. This can, however, be useful if you also want to heat a room slightly.

So why pick a dessicant dehumidifer if they are so much less efficient? 

If the space you want to dehumidify regularly dips below 20&deg;C, then a compressor dehumidifer will be ineffective. See, the relationship between Absolute and Relative humidity is not linear, and as the cold-side has to be kept above 0&deg;C to keep the water from freezing, it’s not possible to create a big enough difference in temperature to encourage condensation.

## Relative and Absolute Humidity

It’s worth asking ourselves what we’re actually doing when we’re dehumidifying the air.

Humidity refers to the amount of evaporated water in the air - tiny droplets of water dissolved into the gas we breathe.

The amount of water the air can hold varies with temperature, so we measure it with *Relative Humidity* - the amount of water in the air as a percentage of the maximum it *could* hold at that temperature.

This is different from *Absolute Humidity*, the weight of water per volume of air, typically measured in grams of water per cubic metre of dry air, or grams of water per kilogram of air. For our purposes, the volumetric g/m^3 is more useful.

The absolute humidity at 100% relative humidity (the saturation curve) is not linear with temperature. This can be seen in a psychrometric-diagram:

![Psychrometric diagram](https://thumb.wikimedia.org/wikipedia/commons/thumb/9/9d/PsychrometricChart.SeaLevel.SI.svg/1920px-PsychrometricChart.SeaLevel.SI.svg.png?utm_source=en.wikipedia.org&utm_campaign=imageinfo&utm_content=thumbnail) (Arthur Ogawa, 2009) (todo, get a psychrometric graph with volumetric absolute humidity)

The top line represents 100% relative humidity, with each black line below that representing select percentages at 10% increments. The x-axis is temperature, and the y-axis is the absolute humidity.

As we move left to lower temperatures on the x-axis, the mass of water in the air at a given relative humidity is lower. This is the principle of a compressor dehumidifier, by reducing the temperature locally in a pocket of air, water that can no longer be held in the air will condense out.

## Beating the marketing

Throughout my product research, I found it opaque whether a dehumidifier I was looking at was a compressor or a dessicant dehumidifier. I found, eventually, I had to look into the user manual or technical datasheets.

If a product uses a refrigerant such as r (todo), it is required to disclose that in the safety information section of the manual. This, I found, was the most reliable way to check if I was looking at a dessicant or a compressor model.

Many dehumidifiers will also make a claim for the size of space they are suitable for, usually in square meters. This is plain nonsense, as the area of a room says nothing without extra information about its volume and its draughtiness.

The most important statistics to look at are: price, extraction rate (usually measured in Litres per day), and power use.

## Draughtiness and Airtightness

How hard your dehumidifier has to work, depends on how leaky your space is. If humid, outdoor air is coming in and replacing the (ideally) dry, inside air, your dehumidifer has to work harder to keep the room at the target humidity.

This is typically measured in Air Changes per Hour, or ACH. A very draughty room, such as a garage or drying area, may have an ACH of 1-1.5, whereas an efficient, tightly sealed room should be lower than 0.6.

## Putting it all together

Okay, with the theory out of the way we can start to calculate the extraction rate we need.
You need to know
- The volume of your room.
- The airtightness of your room in numbers of ACH.
- Your average outside humidity.
- Your target humidity. The comfort range is 40%-60%.
- Your average inside temperature.


Lets start with the easiest thing first:
### Volume
This need not be too exact, especially if you are planning on moving the dehumidifier around. Measure your room’s width, breadth and height, in meters (m). The Volume, in cubic meters (m^3), is found by multiplying these three together:
{% raw %}
$$
    V = w\cdot b\cdot h.
$$
{% endraw %}

### Airtightness
Here, some estimation is required. In my case, I’m dehumidifying a garage with a partition wall, so I went for an ACH of 1.0.

This is used to calculate the volume of air we need to dehumidify, V prime:
{% raw %}
$$
    V^\prime = V \cdot \rm{ACH}.
$$
{% endraw %}
 
### Average outside humidity
Your local meteorological office should have information on this. Where I live, in Glasgow, Scotland, the humidity is 80-90% pretty much year round.


### Calculating the extraction rate needed

The volume of water to remove is found by looking at the psychrometric diagram. First, read the absolute humidity at your average outside relative humidity at your average internal temperature. Next, read the same for your target humidity. Subtract the two to get the mass of water per volume of air that we are trying to remove.

Next, multiply this by V prime from above to get the absolute mass of water:
{% raw %}
$$
    m_{\rm{H_2O}} = \rm{AH}_{\rm{outside}} - \rm{AH}_{\rm{target}} \cdot V^\prime.
$$
{% endraw %}

This gives us the mass, which still isn’t useful when comparing to product specifications, so next we need to divide it by the density of water ($\\rho$, 1,000 kg/m^3 or 1,000 g/L) [todo - cite this] to get this as a volume:

{% raw %}
$$
\begin{align}
    V_{\rm{H_2O}}   &= \frac{m_{\rm{H_2O}}}{\rho} \\
                    &= \frac{m_{\rm{H_2O}}}{1,000}.
\end{align}
$$
{% endraw %}

Finally, multiply this by 24 to get the dehumidification extraction rate in litres per day.

## Plumbing for continuous drainage

Many people simply place their drain hose into a sink, but if you want something neater and more permanent, there’s a few options.

Assuming an extraction rate of 9L/day, and the dehumidifier running at full capacity, this amounts to only 6mL of water per minute, or a very slow trickle. If your dehumidifier isn’t positioned near a sink, it’s perfectly acceptable to drain this outside without a direct sewer connection.

I used 22mm rigid overflow waste pipes and solvent weld fittings. I drilled a hole at a slight angle - to allow water to drain out rather than sitting in the pipe - through the masonry at the bottom of my wall. I ran a pipe through it, with a 90&deg; elbow on the outside to direct the stream out, and another on the inside to run the pipe vertically up to the shelf my dehumidifer is to sit on. If you need a long horizontal run, make sure it runs at a slight angle of at least 1:50 (one metre down for every 50 metres across). Secure the pipe onto the wall with a clip no more than every 500mm.

I terminated this pipe with a solvent weld 22mm overflow tank connector, made by Aquaflow and [available from Toolstation](https://www.toolstation.com/solvent-weld-overflow-tank-connector/p29453) in the UK. This gives us a 3/4” BSP fitting to screw a hose barb onto. I shortened the length of available thread with a hacksaw, using the included nut as a guide.

![product photograph of solvent weld 22mm overflow tank connector, view from south west](https://cdn.aws.toolstation.com/images/141020-UK/800/29453.jpg)

The dehumidifier I picked, the EcoAir DD2, has a fitting for an 11mm drain hose. A barb this size isn’t all that readily available, but I found that a washer inlet hose is a similar diameter and comes with a 3/4” BSP fitting. By cutting one end off of the hose, the now-free end can be softened in a cup of hot water and pressed onto the dehumidifier’s outlet. Alternatively, you can cut through the crimped ends of the washer inlet hose, leaving you with a barb that should accept the softer silicone tubing included with the dehumidifier, plus a zip tie or a hose clip for security.

If your dehumidifier is to be positioned near an existing sink or drain, this makes matters much easier. Simply install a washing machine drain fitting onto your sink trap and push the dehumidifier’s drain hose into or onto the barb.

