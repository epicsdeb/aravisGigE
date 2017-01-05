TOP=../..

include $(TOP)/configure/CONFIG

# -------------------------------
# Build an Diamond Support Module
# -------------------------------

# Build some little helper functions
#PROD_IOC += aravisTest
#aravisTest_SRCS_DEFAULT += aravisTest.c
#aravisTest_LIBS += $(EPICS_BASE_IOC_LIBS)

PROD_IOC += inspectcam
inspectcam_SRCS += inspectcam.cpp

TESTPROD_IOC += testcam
testcam_SRCS += testcam.cpp
testcam_LIBS += aravisCamera ADBase asyn dbCore Com

TESTPROD_IOC += testimage
testimage_SRCS += testimage.cpp
testimage_LIBS += aravisCamera ADBase asyn dbCore Com

LIBRARY_IOC += aravisCamera

# The following are compiled and added to the support library
aravisCamera_SRCS += aravisCamera.cpp

DBD += aravisCameraSupport.dbd

USR_CPPFLAGS += $(shell pkg-config --cflags glib-2.0 aravis-0.6)
USR_LDFLAGS += $(shell pkg-config --libs-only-L glib-2.0 aravis-0.6)
PROD_LDLIBS += $(shell pkg-config --libs-only-l glib-2.0 aravis-0.6)

include $(TOP)/configure/RULES
