# key_value_data_store
This is a file based key-value data store that supports based CRD(create , read and delete) operations . This data store meant to be used as a local storage for one single process on one laptop . This data store must be exposed as a library to clients that can instantiate a class and work with the data store . 

<p>Here's an example given below</p>
<pre>

/**
	 * Constructor initialize the DataStore with default storage location
	 */
DataStore myDataStore = new DataStore();// default location will be "C:\\Users\\Public\\Documents"

/**
	 * Constructor initialize the DataStore with given storage location
	 * 
	 * @param filePath
	 *            the storage location path
	 */
DataStore myDataStore = new DataStore(String filePath);//pass file location

/**
	 * 
	 * Method to create an element in the DataStore
	 * 
	 * @param key
	 *            The key of the element
	 * @param value
	 *            The value of the element
	 * @return status of the operation
	 */
myDataStore.create(String key, JSONObject value);

/**
	 * Method to create an element in the DataStore
	 * 
	 * @param key
	 *            The key of the element
	 * @param value
	 *            The value of the element
	 * @param timeToLive
	 *            Number of seconds after which the element is destroyed
	 * @return status of the operation
	 */
myDataStore.create(String key, JSONObject value, int timeToLive);

/**
	 * Method to read an element from the DataStore
	 * 
	 * @param key
	 *            The key of the element to read the element
	 * @return The value as type of JSONObject
	 */
myDataStore.read(String key)

/**
	 * Method to delete an element from the DataStore
	 */
myDataStore.delete(String key)
</pre>

<p>The sample response of DataStore application given below</p>
<pre>

========================CREATE ==============================

Create operation successful
Operation failed due to key already available
Operation failed due to key already available
Create operation successful
Operation failed due to key length exceeded the limit(32chars)
====================AFTER WAIT===============
Create operation successful
Operation failed due to key already available
Operation failed due to key already available
Operation failed due to key already available

==========================READ===============================

{"firstName":"Ameena","lastName":"Shaik","address:"Guntur"}
Operation failed due to key not available
Operation failed due to key length exceeded the limit(32chars)
====================AFTER WAIT===============
Operation failed due to key not available
{"firstName":"Ameena","lastName":"Shaik","address:"Guntur"}

========================DELETE ==============================
Operation failed due to key not available
Record deletion successful
Operation failed due to key not available
Operation failed due to key not available
Operation failed due to key length exceeded the limit(32chars)
</pre>


