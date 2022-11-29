# Physical Layer
Communication between two adjacent network nodes

Information can be sent in the form of bits - represented by high and low voltages 

## What could possibly go wrong?
1. What happens if there is a magnetic flux through the loop - extra voltage will be generated in the communication channel - **cross talk**
we need to ensure that the cross talk is low - one of the ways is classic **twisted pair** keep the loop area small (tight twisting) 

Categories of twisted pairs:
- CAT 3 : 10 Mbps over 100m 
- CAT 5: 100 Mbps over 100m
- CAT 6: 1 Gbps over 100m

Typical ethernet wire - 8 twisted pairs (typically)

Coaxial cables:
- use explicit insulation
- thin net coax: 100 Mbps over 200m
- thick net coax: 100 Mbps 500m

Optic Fibres:
- cladding - outer covering
- very little loss in reflections
- in practice, different modes (different angled rays) might be sent through the fibre - multi mode fibre - two rays travel different distances - adding them up at the other end might cause distortions - not the best way to communicate

## Attenuation
We look at the log of the ratio of the output to input 

$ Attenuation =  10.log_{10}\frac{P_{in}}{P_{out}} = 20.log_{10}\frac{A_{in}}{A_{out}} $

Usually specified in dB per 1000 feet

1. Say we doubled the length of the wire, what will be the new specification? - total attenuation also twice 

## Feel of the dB scale
let $P_{out} = \frac{1}{2}P_{in}$. Attenuation is roughly 3 dB - half the power was lost

dBm and dBW - are scales for absolute powers

1. dBm: Power = P, but we don't want to write it in absolute units. 

$ P_{dBm units} = 10log_{10}\frac{P}{1mW}$

2. dBW scale: Power P, 

$ P_{dBW \ units} = 10log_{10}\frac{P}{1W}$

## Typical attenuation in wires:
1. Decreasing level of attenuation (with frequency): 
- Cat-3 has more attenuation than Cat-5 > Co-axial (thicknet) 
- Why does it change with frequency? - because of capcitance and inductances
- Higher frequency is generally more attenation

### Optic Fibre
- Attenuation chart (with frequncy):
- non-monotonic
- order of magnitude lower attenuation as compared to Cat-3/Cat-5/Co-axial
- Higher frequency range in which it can be used - Cat-3/Cat-5/Coaxial - attenuation becomes too high for higher frequencies

## Wireless links
1. There is a max limit to power transmitted through wireless
$ P_{out} = \frac{k.P_{in}.A}{d^2}$
- More realistic attenuation: 
$ P_{out} = k.\frac{P_{in}}{d^{\alpha}} \ (2 < \alpha < 5)$

2. Solution - Directional antennas - power is focussed in a beam
3. MIMO - multiple antenna multiple output system - build some amount of directioanlity
4. Latest - Massive MIMO 

## What can go wrong in wireless:
1. Intereference:
- cross talk between signals - can be reduced in wires by twisting
2. Obstructions:
- Absorptions - but some signal can go around - diffraction
3. Multipaths:
- reflections from objects around in addition to the direct path
- The reflection is a bit delayed
- Or flipped 
- The total signal might be different
- We don't know how many multipaths will be there








