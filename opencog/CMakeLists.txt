
# The atom_types.h file is written to the build directory
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR})

# The build order used here is loosely in terms of 
# dependencies: the later parts depend on, or may
# someday depend on the earlier parts.
#
ADD_SUBDIRECTORY (util)
ADD_SUBDIRECTORY (comboreduct)
ADD_SUBDIRECTORY (reasoning)
ADD_SUBDIRECTORY (learning)

IF (HAVE_ATOMSPACE)
    #ADD_SUBDIRECTORY (atomspace)
    #ADD_SUBDIRECTORY (benchmark)
    #ADD_SUBDIRECTORY (query)
    #ADD_SUBDIRECTORY (nlp)
    #ADD_SUBDIRECTORY (persist)
ENDIF (HAVE_ATOMSPACE)

IF (HAVE_ATTENTION)
   # ADD_SUBDIRECTORY (dynamics)
ENDIF (HAVE_ATTENTION)

IF (HAVE_SERVER)
   # ADD_SUBDIRECTORY (server)
ENDIF(HAVE_SERVER)

IF (HAVE_WEB)
   # ADD_SUBDIRECTORY (web)
ENDIF (HAVE_WEB)

# There is nothing in this directory?
#IF (NOT WIN32)
#ADD_SUBDIRECTORY(modules)
#ENDIF (NOT WIN32)

# Extension language support
IF (HAVE_GUILE)
        #ADD_SUBDIRECTORY (guile)
        #ADD_SUBDIRECTORY (scm)
        #ADD_SUBDIRECTORY (shell)
ENDIF (HAVE_GUILE)

IF (HAVE_CYTHON)
        #ADD_SUBDIRECTORY (cython)
ENDIF (HAVE_CYTHON)

IF (HAVE_SERVER)
    #ADD_SUBDIRECTORY (spacetime)
    #ADD_SUBDIRECTORY (spatial)
ENDIF (HAVE_SERVER)

IF (HAVE_EMBODIMENT)
        #ADD_SUBDIRECTORY (embodiment)
ENDIF (HAVE_EMBODIMENT)

# Graphics and visualization subsystems
IF (HAVE_SERVER)
   #ADD_SUBDIRECTORY (dotty)
   IF (HAVE_UBIGRAPH)
      #ADD_SUBDIRECTORY (ubigraph)
   ENDIF (HAVE_UBIGRAPH)
ENDIF (HAVE_SERVER)
