In production grade application we want to run the task parallely to save the time. 
Here we dot need to use packages like asynvc IO or IF multitreading beacuse langgraph will handle everything for us. 

There can be drawback for using asynchronous execution of nodes, and one of them is state config. 
Here nodes that modify the same attribute in the state can potentially each others changes, so this will lead to inconsistent and unexpected results and potentially can lead to race conditions. 

and can lead to data inconsistencies, and also debugging asynchronously. 

The best practice for using asynchronous execution of nodes is to isolate the state updates. So each node should write to a different attribute in the state to aviod those conflicts .