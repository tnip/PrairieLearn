
.PHONY: text

comma := ,
CONFIG_COURSE_DIR := $(shell grep -s courseDir config.json)
CONFIG_COURSE_DIR := $(strip $(CONFIG_COURSE_DIR))
CONFIG_COURSE_DIR := $(patsubst "courseDir":%,%,$(CONFIG_COURSE_DIR))
CONFIG_COURSE_DIR := $(strip $(CONFIG_COURSE_DIR))
CONFIG_COURSE_DIR := $(patsubst "%"$(comma),%,$(CONFIG_COURSE_DIR))
COURSE_DIR := $(if $(CONFIG_COURSE_DIR),$(CONFIG_COURSE_DIR),../exampleCourse)

QUESTIONS_DIR := $(COURSE_DIR)/questions
CLIENTCODE_DIR := $(COURSE_DIR)/clientCode

text:
	../tool/generate_text.py ../frontend/text $(QUESTIONS_DIR)
	../tool/generate_text.py ../frontend/text $(CLIENTCODE_DIR)
