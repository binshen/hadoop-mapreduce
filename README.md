
hadoop jar ~/BigData/hadoop-2.7.3/share/hadoop/tools/lib/hadoop-streaming-2.7.3.jar
    -mapper ~/test/ruby/max_temperature_map.rb
    -reducer ~/test/ruby/max_temperature_reduce.rb
    -input /test/input
    -output /test/output/x1

hadoop jar ~/BigData/hadoop-2.7.3/share/hadoop/tools/lib/hadoop-streaming-2.7.3.jar
    -mapper ~/test/python/max_temperature_map.py
    -reducer ~/test/python/max_temperature_reduce.py
    -input /test/input
    -output /test/output/x2

================================================================

hadoop jar ~/BigData/hadoop-2.7.3/share/hadoop/tools/lib/hadoop-streaming-2.7.3.jar
    -file ~/test/python/max_temperature_map.py
    -mapper 'python max_temperature_map.py'
    -file ~/test/python/max_temperature_reduce.py
    -reducer 'python max_temperature_reduce.py'
    -input /input
    -output /x3