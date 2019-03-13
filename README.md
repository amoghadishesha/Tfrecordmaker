# Tfrecordmaker
Image directory to tensorflow records

If you are working with large datasets, using a binary file format for storage of your data can have a significant impact on the performance of your import pipeline and as a consequence on the training time of your model. Binary data takes up less space on disk, takes less time to copy and can be read much more efficiently from disk. This is especially true if your data is stored on spinning disks, due to the much lower read/write performance in comparison with SSDs.
A TFRecord file stores your data as a sequence of binary strings. This means you need to specify the structure of your data before you write it to the file. Tensorflow provides two components for this purpose: tf.train.Example and tf.train.SequenceExample. You have to store each sample of your data in one of these structures, then serialize it and use a tf.python_io.TFRecordWriter to write it to disk.


Note: the example proto in the utils file has a particular order in which data is written into the tfrecord file. this has to match your tfrecord reader.
