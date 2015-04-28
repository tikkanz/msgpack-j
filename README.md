# msgpack-j 
Implementation of the Message Pack serialization format in J

# WORK IN PROGRESS
==================
# Examples
# strings
pack 'hello world'

�hello world

unpack �hello world

'hello world'

#Usage
======
#Packing data

pack: Packs J nouns to a byte string.
packObj: Packs J nouns to a hex string representation of the bytes.

Example:
pack 2;4.67;'hello, world'

��@┐�┼z�G��hello, world

packObj 2;4.67;'hello, world'

9302cb4012ae147ae147aeac68656c6c6f2c20776f726c64

#Unpacking data

unpack: Unpacks a byte string to JSON objects 
unpackObj: Unpacks a hex string representation to JSON objects.

Example: unpackObj '81a46461746183a2696401a673636f72657394cb400999999999999acb4016cccccccccccdcb40091eb851eb851fcb4007333333333333a56f7468657283a4736f6d65d1f2b8a46d6f7265ccc8a4646174610c'

{"data":{"id":1,"scores":[3.2,5.7,3.14,2.9],"other":{"some":_3400,"more":200,"data":12}}}

#TODO
Currently the packing/unpacking is not symmetric. Unpacking produces JSON, but should also be able to produce J objects.
To do this, a hashmap implementation in J needs to be constructed. Without that, it is not feasible to deserialized JSON to J consistently.

