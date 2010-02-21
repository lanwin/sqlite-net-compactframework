sqlite-net .Net Compact Framework Port 
==============
This is a port of sqlite-net http://code.google.com/p/sqlite-net to Microsoft .Net Compact Framework (CF). CF has some limitation for .Net interop so it can not run out of the box on it (in example long or double as return types are not supported). So ive created an special version of the sqlite interop dll from the ADO.Net sqlite dataprovider http://sqlite.phxsoftware.com/. This version adds the missing sqlite3_last_insert_rowid_interop function. 
In sqlite-net i only changed the SQLite3 class which simply calls the native sqlite3.dll.

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
    
Compiling sqlite_interop
============
To compile sqlite_interop you need the Visual Studio 2008 C++ compiler. It dose not contains the sqlite source code. So you have to download the latest source version from http://sqlite.org/download.html and extract it to sqlite_interop/Sources/splitsource.
	
Issues
============
If you found issues and think they are coming from Compact Framework port, then you can put them in to the issue tracker here. All others you can report here http://code.google.com/p/sqlite-net

Ported from
============
- Steve Wagner (lanwin)