
ASSEMBLY = $(top_builddir)/build/bin/mdtool.exe

FILES = src/AssemblyInfo.cs \
src/mdtool.cs

all: $(ASSEMBLY) $(ASSEMBLY).config

REFS = $(MONO_ADDINS_LIBS) \
	$(MONO_ADDINS_SETUP_LIBS)

DEPS = $(top_builddir)/build/bin/MonoDevelop.Core.dll
	
$(ASSEMBLY): $(build_sources) $(DEPS)
	$(CSC) $(CSC_FLAGS) $(build_sources) $(REFS) $(build_deps) /out:$(ASSEMBLY)

$(ASSEMBLY).config: $(ASSEMBLY) $(srcdir)/app.config
	cp $(srcdir)/app.config $(ASSEMBLY).config

assemblydir = $(MD_ASSEMBLY_DIR)
assembly_DATA = $(ASSEMBLY) $(ASSEMBLY).mdb $(ASSEMBLY).config

CLEANFILES = $(ASSEMBLY) $(ASSEMBLY).mdb $(ASSEMBLY).config
EXTRA_DIST = $(FILES) app.config

include $(top_srcdir)/Makefile.include
