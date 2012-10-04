XmlRpcCS
========

## Download

Homepage: [XmlRpcCS](http://opaque.ods.org/XmlRpcCS/)

Package: [XmlRpcCS-1.10.zip](http://opaque.ods.org/XmlRpcCS/XmlRpcCS-1.10.zip)

## Introduction

This package provides a simple XML-RPC client and server for C# applications.
Possibly any .NET applications though I've not tested that. It's pure C#,
using the stock .NET assemblies and nothing else.

The goals of XmlRpcCS were to keep it small and simple. The motivation was to
write something that was easy to use while being flexible.

## Notable Features

  * Fully XML-RPC specification compliant, including key extensions. 
  * Simple client (XmlRpcRequest) 
  * Complete single class embeddable server (XmlRpcServer) 
  * XML-RPC System object implemented (XmlRpcSystemObject) 
  * Method level exposure granularity (XmlRpcExposedAttribute)
  * Mono support (See [Mono](docs/MONO.html)) 
  * .NET Compact Framework support (See [CF](docs/CF.html)). 
  * Option of dynamic local proxies.

## Prerequisites to Build

  * Have .NET SDK loaded (version >= 1.0) 
  * Have csc and friends in your PATH. 
  * Put nant/bin into your PATH (nant is an OpenSource C# build tool, minimal binaries included in ./nant)

## To Build

In a command shell:

    
       nant -find all
    

## Basic Test

Open two command shells, in one:

    
         SampleServer
    

In the other:

    
         SampleClient
    

## Documentation

  * The API documentation: [Documentation](docs/classes/XmlRpcCS.html)
  * The descriptions of the type mapping: [Types](docs/TYPES.html)
  * A UML doodle about the serialize/deserialize class inheritance: [Serialization](docs/XmlRpcSerialization.png)

## Sample Code

Under src/samples there are examples. Read the [Examples](docs/EXAMPLES.html)
for more info.

## Unit Tests

Under tests/ there are some basic unit tests. To run them have NUnit
installed, edit the path to NUnit in xmlrpccs.build and then:

    
    	nant -find unit-tests

Why didn't I use nant's nunit task you ask? It's rather broken.

## License

XmlRpcCS is under the BSD license. See: [License](LICENSE.html)

## References

  * [xmlrpc.org](http://xmlrpc.org) To learn more about XML-RPC. 
  * [nant.sourceforge.net](http://nant.sourceforge.net) To learn more about nant. 
  * [nunit.sourceforge.net](http://nunit.sourceforge.net) To learn more about NUnit unit testing.
  * [go-mono.net](http://go-mono.net) To learn more about the mono project 

## To Do

  * Support system object "capabilities" method
  * Improve system object's "methodHelp" support - rip from XML docs somehow.
  * Method overloading based on arguements
  * More unit tests
  * Tutorial doc

## Changes

Version Date Changes

1.10

200300617

Support for dynamic local proxies.

Bug fix to XmlRpcException.ToString()

Bug fix to XmlRpcServer Stop/Start

1.9

20030425

.NET Compact Framework compatible

XSL method doc extraction for system.methodHelp

Stop() method on XmlRpcServer (Thanks: "Chris" <chris@bartling.net>)

1.8

20030415

Threaded XML-RPC responses behind the XmlRpcServer

Collection types moved to interfaces at all levels.

methodHelp system method basic implementation.

Bug fix, null returns throw an exception.

AssemblyInfo standard class added.

mime type "test" -> "text" typo fix (Thanks: "Tony" <platoduck@hotmail.com>)

Request buffering fix. (Thanks: "Tony" <platoduck@hotmail.com>)

1.7

20030404

build cleanups

initial mono support

bugfix in XmlRpcServer's string building

1.6

20030325

Fixed a deserializer bug with structs in structs

Better look to documentation I think

Google example

Some performance improvements

A few unit tests.

1.5

20030301

Improve document formatting and content.

Some code refactoring.

1.4

20030217

XLST for /doc XML -> HTML

Documentation

1.3

20030210

Boxcaring supported (major speed up under correct conditions!)

Request deserializer bug fix

Various refactorings, particularly Invoke method

Samples improved

Notes improved

1.2

20030130

Introspection via "system" object

Added optional XmlRpcExposed Attribute

Moved to using "is" operator...damn C# is syntax fat

Fix known deserializer bug pertaining to containers (array/struct) in
containers

1.1

20030128

Bug fix in request deserializer

Better samples

response.FaultCode/.FaultString added

indentation on the XML in ToString of request/response

1.0

20030125

Support for base64

Use .NET's XmlWriter

Centralize XML-RPC tokens into XmlRpcXmlTokens

[nwc@bigfoot.com](mailto:nwc@bigfoot.com)

