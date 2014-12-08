> ***I havent any plan to update that code to a nerwer version, since I have no compact device anymore and in my spare free time there are enought other projects. So feel free to send a pullrequest if you want a newer version.***

sqlite-net .Net Compact Framework Port 
==============
This is a port of sqlite-net http://code.google.com/p/sqlite-net to Microsoft .Net Compact Framework.

Compact Framework has some interop limitations so it can not run sqlite-net out of the box (in example long or double as return types are not supported). 

First Compact Framework has no System.Linq.Expressions. This issue can be solved since db4o has ported the Mono Linq.Expressions to Compact Framework. https://source.db4o.com/db4o/trunk/db4o.net/Libs/compact-3.5/System.Linq.Expressions/

Second you need a special version of sqlite3.dll which has special interop for Compact Framework. A lot of that code is provided by the SQLite DataProvider from http://sqlite.phxsoftware.com/, but it dose not have the required sqlite3_last_insert_rowid_interop function, so ive created a fork of it here, unter Sqlite3.

Ive also added a simple dll project which uses the sqlite.cs file from root and creates an assembly from it, for all people which dose not want to include the cs file directly.

About sqlite-net
==============
Homepage: http://code.google.com/p/sqlite-net

sqlite-net is an open source, minimal library to allow .NET and Mono applications to store data in SQLite 3 databases. It is written in C# 3.0 and is meant to be simply compiled in with your projects. It was first designed to work with MonoTouch  on the iPhone, but should work in any other CLI environment.

sqlite-net was designed as a quick and convenient database layer. Its design follows from these goals:

* Very easy to integrate with existing projects and with MonoTouch projects. 
* Fast and efficient. 
* Methods for executing queries safely (using parameters) and for retrieving the results of those query in a strongly typed fashion. 
* Linq support so that you don't have to write SQL (see LinqSupport). 
* Works with your data model without forcing you to change your classes. (Contains a small reflection-driven ORM layer.) 
* It has 0 dependencies aside from a compiled form of the sqlite3 library. 

Non-goals include:
* Not an implementation of IDbConnection and its family. This is not a full SQLite driver. If you need that, go get System.Data.SQLite or csharp-sqlite. 
    
sqlite-net license
============
Copyright (c) 2009-2010 Krueger Systems, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
	
Compiling Sqlite3
============
To compile Sqlite3 you need the Visual Studio 2008 C++ compiler. It dose not contains the sqlite source code. So you have to download the latest source version from http://sqlite.org/download.html and extract it to Sqlite3/Sources/splitsource.
	
Issues
============
If you found issues and think they are coming from Compact Framework port, then you can put them in to the issue tracker here. All others you can report here http://code.google.com/p/sqlite-net

Ported from
============
- Steve Wagner (lanwin)
