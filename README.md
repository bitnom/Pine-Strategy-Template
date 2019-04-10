# Pine-Strategy-Template
 Description:
 ============

 This crossover strategy is just a place holder.
 This is really just a template for you to build your own strategy for backtesting.
 And then to run with autoview.

 I included the crossover strategy so it would work out of the box and you'd
 have simple example code to modify.

 It does however provide a lot of flexibilty for what you build, and it is
 very easy to switch between Strategy and Alerts. You can completely switch
 between Strategy and Alerts with a single Comment / Uncomment of the blocks
 at the top of the script and have confidence that the script will run the same
 in both states.

 Other than that you should only need to edit code in the section:
 between // BEGIN ACTUAL STRATEGY and // END ACTUAL STRATEGY

 It supports Renko and HA candles (please take care with both to understand
 what you are actually backtesting). See notes below.

 It supports Multiple Timeframes (via a multiplier)

 it can be long only short only or both. You can specify different
 Long Close and Short Open (and Short Close / Long Open) conditions
 or let them be the same.

 In fact you define your whole strategy by just setting those 4 variables.

You can set specific time periods to backtest (or to run the alerts)

 Support for various stops:
  - Trailing Stop, with Activate Level (as % of price) and Trailing Stop (as % of price)
  - Target Profit Level, (as % of price)
  - Stop Loss Level, (as % of price)

 You can monitor real or hypothetical trades (and stops)
  - BUY green triangles and SELL dark red triangles
  - Trade Order closed colour coded Label:
      > Dark Red = Stop Loss Hit
      > Green  = Target Profit Hit
      > Purple = Trailing Stop Hit
      > Orange = Opposite (Sell) Order Close
  - Trailing Stop Activate Price = Blue dotted line
  - Trailing Stop Price =  Fuschia solid stepping line
  - Target Profit Price = Lime '+' line
  - Stop Loss Price = Red '+' line


 References:
 ===========
 - MA Ribbon R0.13 by TensorTom
 - Original script bt JustUncleL

 Dealing With Renko Charts:
 --------------------------
 - If you choose to use Renko charts, make sure you have enabled the "IS This a RENKO Chart"
   option.
 - If you want non-repainting Renko charts you MUST use TRADITIONAL Renko Bricks. This
   type of brick is fixed and will not change size.
 - Also use Renko bricks with WICKS DISABLED. Wicks are not part of Renko, the whole
   idea of using Renko bricks is not to see the wick noise.

 Working with HA Candles:
 ------------------------
 Regardless of what you display on your chart HA or traditional Candlesticks
 the dafaults of this are set to use the tradional candlestick values to save you
 from bogus HA backtests.
 HOWEVER
 Regardless of what you display on your chart HA or traditional Candlesticks, you
 may run a startegy (or a backtest, but why?) on HA values by selecting:
 "Use Heikin-Ashi Candles".

 Revisions:
 ==========
 R0.13B  - [MrBit] Branch from JustUncleL R0.13
           > Remove actual algo
           > Establish functions for long Signal, long Close Signal
             and short Signal, short Close Signal to minimize the places code
             must be editted to update / replace algos
           > Make allow Long and allow short and invert trade directions
             independent options
           > Added support for alternate candle types
           > Added autoset backtest period feature, and optional coloring
           > Moved strategy calls in to functions so they can all be comment
             out or activated / disabled in  a single block at the top of the script
 R1.00  - Extensive Clean up and bug fixes
          > Enabled testPeriod to be used to limit Alerts too
          > You can completely switch between Strategy and Alerts with a single
            Comment / Uncomment of the blocks at the top
          > Added a trivial strategy so it works out of the box.
          > Renamed to Simple Template 1.00

 TODO:   Scaling / Pyramding


-----------------------------------------------------------------------------
Copyright 2019 TensorTom, JustUncleL, MrBit (yatrader2)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

The GNU General Public License can be found here
<http://www.gnu.org/licenses/>.

-----------------------------------------------------------------------------
