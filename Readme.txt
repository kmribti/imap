IMAP client implmentation using Poco C++ framework, work are in progress but the code are quite usable for basic operations.

This code has been tested only with VS2015 build type.

Sample code:

   
   typedef std::vector<IMAPClientSession::FolderInfo> folders_type;
   
   try {
      IMAPClientSession  imap(host, port);
	  imap.login (user, password);
	  
	  folders_type  Folders;
	  
	  imap.listFolder("", Folders);
	  
	  for (auto f: Folders)
	  {
	      std::cout << f.name << std::endl;
	  }
	  
	} catch (IMAPException e) {
	   std::cout << e.message() << std::endl;
	}
	  
   