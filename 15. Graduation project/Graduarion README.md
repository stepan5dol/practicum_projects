# Industy
## Intro

In order to optimize production costs, the metallurgical combine LLC "So Temper steel" decided to reduce electricity consumption at the steel processing stage. You have to build a model that predicts the temperature of steel.

## Description of the processing stage

Steel is processed in a metal bucket with a capacity of about 100 tons. In order for the bucket to withstand high temperatures, it is lined with refractory bricks from the inside. The molten steel is poured into a ladle and heated to the desired temperature with graphite electrodes. They are installed in the bucket lid. 

Sulfur is removed from the alloy (desulfurization), the chemical composition is corrected by adding impurities and samples are taken. Steel is alloyed — its composition is changed — by feeding alloy pieces from a hopper for bulk materials or wire through a special tribe apparatus (English tribe, "mass").

Before the first time alloying additives are introduced, the temperature of the steel is measured and its chemical analysis is performed. Then the temperature is increased for a few minutes, alloying materials are added and the alloy is purged with an inert gas. Then it is mixed and measurements are carried out again. This cycle is repeated until the target chemical composition and optimal melting temperature are reached.

Then the molten steel is sent to the metal finishing or enters the continuous casting machine. From there, the finished product comes out in the form of slabs (Eng. *slab*, "slab").

## Data Description

The data consists of files received from different sources:

- `data_arc.csv` — data about electrodes;
- `data_bulk.csv` — data on the supply of bulk materials (volume);
- `data_bulk_time.csv` *—* data on the supply of bulk materials (time);
- `data_gas.csv` — data on gas purging of the alloy;
- `data_temp.csv` — temperature measurement results;
- `data_wire.csv` — data on wire materials (volume);
- `data_wire_time.csv` — data on wire materials (time).

In all files, the `key` column contains the batch number. There may be several lines with the same `key` value in the files: they correspond to different processing iterations.
