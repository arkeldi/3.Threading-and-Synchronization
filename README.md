# <p align="center">Threading and Synchronization<p>

**Introduction**

This project is an extension of 'Client-Server IPC using Named Pipes' with integrated multithreading to increase efficiency and improve on the runtime.

While preparing the timing report for 'Client-Server IPC using Named Pipes', I noticed that transferring over multiple data points (1K) took a long time to complete. This was also observable when using filemsg requests to transfer over raw files of extremely large sizes.

The reason behind this undesirable runtime is that I was using a single channel to transfer over each data point or chunk in a sequential manner. In this project, I will take advantage of multithreading to implement our transfer functionality through multiple channels in a concurrent manner; this will improve on bottlenecks and make operations significantly faster.

The code analysis document(pdf) I have attached go into depth of the program. 

**Tasks**

- [ ] Implement the BoundedBuffer class
  - [ ] write the BoundedBuffer::push(char*, int) function
  - [ ] write the BoundedBuffer::pop(char*, int) function
- [ ] Write functions for threads
  - [ ] patient_thread_function
  - [ ] file_thread_function
  - [ ] worker_thread_function
  - [ ] histogram_thread_function
- [ ] Create channels for all worker threads before creating threads
- [ ] Create all threads in client's main
  - [ ] patient threads and histogram threads for datapoint transfers
  - [ ] file threads for file transfers
  - [ ] worker threads for both
- [ ] Join all threads
- [ ] Close all channels
