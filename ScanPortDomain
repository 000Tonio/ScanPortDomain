import socket
import subprocess
import sys , time
from progressbar import *
import progressbar
from datetime import datetime
class COLOR:
	GREEN = '\033[92m'
	YELLOW = '\033[93m'
	FAIL = '\033[91m'
	END = '\033[0m'
	REDS = '\033[91m'
	WHITE = '\033[97m'
	BOLD  = '\033[1m'
	RED   = '\033[91m'
	Black = '\033[90m'
widgets=['Chargement : ',
COLOR.YELLOW          , Percentage()                        , COLOR.END,
COLOR.RED + COLOR.BOLD, Bar(left=' ', marker='━', right=' '), COLOR.END,
COLOR.YELLOW          , Timer()                             , COLOR.END
]

a = 0

remoteServer = input("Entrer une ip ou un domain : ")
remoteServerIP = socket.gethostbyname(remoteServer)


print ("-" * 60)
print ("Scanne en cours de l'ip", remoteServerIP)
print ("-" * 60)
pbar = ProgressBar(widgets=widgets, maxval=1025).start()


try:
    for port in range(1,1025):
    	a = a + 1
    	sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    	result = sock.connect_ex((remoteServerIP, port))
    	pbar.update(a)
    	#pb.update(a)
    	time.sleep(0.1)
    	if result == 0:
    		print ("Port {}: Open".format(port))
    		
    	sock.close()
    
    else:
    	print("FINI")	
except KeyboardInterrupt:
    print ("\nGood bye")
    sys.exit()

except socket.gaierror:
    print ('\nErreur hostname non trouvé !')
    sys.exit()

except socket.error:
    print ("\nConnexion impossible")
    sys.exit()
