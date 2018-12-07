OUTPUT    := build
SRC_DIR   := src
JFLAGS    := -d $(OUTPUT) -sourcepath $(SRC_DIR)
JAVAC     := javac

PACKAGES  := lox
SRC_DIR   := $(addprefix $(SRC_DIR)/com/lowlevel/,$(PACKAGES))

SRC       := $(foreach sdir,$(SRC_DIR),$(wildcard $(sdir)/*.java))
CLASS     := $(SRC:.java=.class)

all: output $(CLASS) jar

output:
	mkdir -p $(OUTPUT)

%.class: %.java
	$(JAVAC) $(JFLAGS) $<

jar:
	jar cvfm lox.jar META-INF/MANIFEST.MF -C build/ .

clean:
	rm -rf $(OUTPUT) lox.jar

