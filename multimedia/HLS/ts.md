# TS
```
							
							|
							|	+---------------+           	  +-----+
video   +-------------+	    |   |   			|video PES		  |     |
------->|video encoder|-----+-->|	Packetizer 	|-----------+---->|     |
data 	+-------------+		|	|				|		 	|	  |	PS  |
							|	+---------------+		 	|	  |		|      Program
							|								|	  |		|--------------------->
							|	+---------------+		 	|	  |		|		Stream
audio   +-------------+	    |   |   			|audio PES  |     | mux |
------->|audio encoder|-----+-->|	Packetizer 	|----+------+---->|     |
data 	+-------------+		|	|				|	 |	 	|	  |	    |
							|	+---------------+    |      |	  +-----+
							|						 |		|				
							|	         		     |      |	  +-----+
							|						 |		|	  |		|
							|						 |		+---->|		|
							|						 | 			  |	TS	|
							|						 |			  | 	|		Transport
							|						 |			  |		|--------------------->
							|						 |			  |		|		Stream
							|						 |			  |	mux	|
							|						 +----------->|		|
							|						 			  |		|
							|						 			  +-----+
							|		Extent of Systems specification
							|<----------------------------------------------------------------->
```
