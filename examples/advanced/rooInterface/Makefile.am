include $(top_srcdir)/examples/Makefile-common.am

## Requires BAT build with RooStats enabled
if ROOSTATS

noinst_PROGRAMS = runRooInterface

runRooInterface_SOURCES = runRooInterface.cxx

input_workspaces = \
	WS_GaussOverFlat.root \
	WS_GaussOverFlat_withSystematics.root \
	WS_Poisson.root \
	WS_Poisson_withSystematics.root

$(input_workspaces): WS_%.root: PrepareWorkspace_%.C
	$(ROOTEXEC) -l -b -q $<

TEST_EXTENSIONS += .root
ROOT_LOG_COMPILER = $(builddir)/runRooInterface

# Disabled:
# TESTS = $(input_workspaces)

endif