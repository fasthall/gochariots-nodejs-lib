# gochariots-nodejs-lib
Node.js library for GoChariots

## Quickstart

    var Record = require('./record.js');
    var gochariots = require('./gochariots.js');

    var seed = 9527;
    var host = 'localhost:8080'
    gochariots.setHost(host)

    var record1 = new Record(seed);
    // Add record content as key-value pairs
    record1.add('first', 'event');
    // Get the hash of the first record
    var hash1 = gochariots.getHash(record1);

    var record2 = new Record(seed);
    record2.add('second', 'event');
    // Set the prerequisite hash of the second record
    record2.addHash(hash1[0])

    // Post the records
    gochariots.post(record2)
    gochariots.post(record1)