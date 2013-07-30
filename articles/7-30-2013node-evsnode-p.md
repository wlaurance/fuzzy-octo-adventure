{"title":"node -e vs node -p","date":"7-30-2013","author":"wlaurance"}

The difference between `node -e` and `node -p` is p will run the script
through the interpretor and print the results. The -e will only evaluate
the script. The time -e will print anything is if something writes to
stdout or stderr.

###node -p
<script src="https://gist.github.com/wlaurance/6117313.js"></script>

###node -e
<script src="https://gist.github.com/wlaurance/6117321.js"></script>


