### SeqtoSql 
- https://arxiv.org/pdf/1709.00103.pdf

The paper talks about how to use a SeqtoSeq deep learning model in to extract information from a text and generate the equalivalent SQL queries. To unfold the problem, they used two techniques one is Seq2Sql and the other one is Wiki2Sql. Wiki2Sql uses a crowed soruced dataset to generate the sql and the earlier is the deep learning network architecture.

Augumented pointer network architecture is used to generate the query from the input. The input to the model is the question and the table content and the output would be a Sql query and and the corresponding result from the output (This we can use it for the Swagger api identification problem to cull the response from the outputs).

The deep learning model is separated into 3 components for generating the query. The first operation is an aggregation operation (Select, Count, etc). The second operation is column in the input table ( Table column names to be added with aggreagation operation). Both the above operations are generated using cross entrophy loss. And the third operation is trained using policy gradient, which the "WHERE" clause condition of a query language.

Wikisql is the dataset used to build the model, this dataset is crowd sourced using Amazon Mechanical Turk. Some of the question & answer datasets hand marked.
		
		WikiSQL 80654 yes 24241
		Geoquery 880 yes 8
		ATIS 5871 yes* 141
		Freebase917 917 yes 81*
		Overnight 26098 yes 8
		WebQuestions 5810 no 2420
		WikiTableQuestions 22033 no 2108
		

All the models were built using pytorch for training the WHERE clause, they used "teacher forcing" (i.e. the policy is not learned from scratch) technique and later implement re-enforcement learning.

The paper talks about, 

* How to collect the datasets neccessary to build the solutions
* How re-enforcement learning is implemented 
* How the reward system is planned
* Benchmark with various implementation, model with re-enforcement and without re-enforcement.

##References

https://github.com/salesforce/WikiSQL -> WikiSQL dataset
http://turing.cs.washington.edu/papers/nli-iui03.pdf -> natural language interfaces is PRECISE