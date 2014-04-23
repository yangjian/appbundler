appbundler
=============

A fork of the [Java Application Bundler](https://svn.java.net/svn/appbundler~svn) 
with single change: support command line arguments.

With this change, you can pass commane line arguments to the Java application like this:

     PATH_TO_THE_APP/Contents/MacOS/JavaAppLauncher [args]
     
Or open the application with arguments:

     open PATH_TO_THE_APP p[--args args1 ...]
     
You can also pass arguments to the Java application with [NSWorkSpace](https://developer.apple.com/library/mac/documentation/cocoa/reference/applicationkit/classes/nsworkspace_class/reference/reference.html) API

	NSURL *appURL = URL_OF_THE_APP;
	
    NSDictionary *dict = nil;
	// prepare the arguments and write them into dict ...
	
    NSWorkspace *workspace = [NSWorkspace sharedWorkspace];
    app = [workspace launchApplicationAtURL:appURL
                                    options:0 
                              configuration:dict
                                      error:&error];
