# gekkoga
Genetic Algorithm for solving optimization of trading strategies using Gekko
## Installation
1) git clone https://github.com/gekkowarez/gekkoga.git
2) cd gekkoga
3) npm install
4) cp config/sample-config.js config/your-config.js
5) modify your-config.js make sure you have data for currency/asset pair and the daterange
6) node run.js -c config/your-config.js
#### tmux usage:
1) sudo apt-get install tmux
2) tmux new -s gekkoga
3) go to the web folder in your gekko installation (gekko/web)
4) node –max-old-space-size=8192 server.js
5) hold CTRL and press b, then press % (to split the screen)
6) goto your gekkoga clone directory
7) node run.js -c config/your-config.js 
8) hold CTRL and press b, then hit d (to detach and run in the background)
9) tmux attach -t gekkoga (to reattach and bring gekkoga to foreground)

#### Stuff from related webpage
http://gekkowarez.com/gekko-genetic-algorithm/

Update!
Along with Generalectric and others a new version of the GA is now to be found here:
https://github.com/gekkowarez/gekkoga

It does have an updated approach that makes the whole thing simpler to use and maintain.

One of the most exciting things that we’ve put together for Gekko is a Genetic Algorithm (GA). A GA is essentially a piece of code that follows the principles of evolution to find optimal settings to reach a goal. In the case of Gekko, commodity, and cryptocurrency trading this means the GA will be calculating the combination of technical analysis thresholds and parameters that return the highest return in a backtest. These values can then be used in live trading conditions.

Installation and usage instructions
This assumes you have Gekko installed – should be compatible with 0.5.2 through to 0.5.9.

Note: version incompatibilities are usually connected to changes made in the config setup (so check if config.js has changed in the gekko repo).

1) go to gekko/ (your gekko install directory)

2) git clone https://github.com/gekkowarez/gekkoga.git (clone gekkoga from the repo)

3) npm install random-ext

4) npm install fs-extra

5) in the config subdirectory, copy sample-config.js to your-new.js

6) change the settings to match your preferred configuration

7) save the file.

Then lets run the GA. (2 options)

Option #1:

Open 2 terminals / command windows

In terminal 1:

1) go to gekko/web

2) node –max-old-space-size=8192 server.js

Now the Gekko api server is running we can run the GA.

In terminal 2:

1) go to gekko/gekkoga

2) node run -c config/your-new.js

At the end of every epoch you will see the winner for that epoch, and you will see the overall winner across all the epochs running in that session. This will all appear in terminal 2.

Option #2:

1) sudo apt-get install tmux

2) tmux new -s gekkoga

3) go to gekko/web

4) node –max-old-space-size=8192 server.js

5) hold CTRL and press b, then press % (to split the screen)

6) go to gekko/gekkoga

7) node run.js -c config/your-new.js

8) hold CTRL and press b, then hit d (to detach and run in the background)

9) tmux attach -t gekkoga (to reattach and bring gekkoga to foreground)

To switch between the split screens you can use CTRL-b then press arrow left or right.

To scroll up or down you can use CTRL-b then press [ and you can then use arrows up or down. Press escape to exit scroll mode.

Limitations of backtesting and genetic algorithms
Essentially the GA is optimizing the config thresholds and parameters against historical data and scenarios (e.g. bull divergence, down trend and so on) and of course if those scenarios are not encountered in live trading your settings may not be appropriate.
