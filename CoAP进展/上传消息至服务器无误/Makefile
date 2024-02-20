#定义编译器和编译选项
CC = gcc
CFLAGS = -Wall -g

#定义目标文件和源文件列表
SRC_DIR = .
CORE_DIR = ./core
PORTFILES_DIR = ./portfiles
EXTERN_DIR = ./external/mbedtls

UTILS_DIR = $(CORE_DIR)/utils
SYSDEP_DIR = $(CORE_DIR)/sysdep

#定义头文件搜索路径
INCLUDE_DIRS = -I$(CORE_DIR) -I$(UTILS_DIR) -I$(SYSDEP_DIR) -I$(EXTERN_DIR)/include/mbedtls -I$(EXTERN_DIR)/include


#源文件
SRC_FILES = \
    $(SRC_DIR)/coap_hangxin.c \
    $(CORE_DIR)/aiot_coap_api.c \
	$(CORE_DIR)/aiot_state_api.c \
	$(CORE_DIR)/sysdep/core_sysdep.c \
	$(CORE_DIR)/sysdep/core_adapter.c \
	$(CORE_DIR)/utils/core_auth.c \
	$(CORE_DIR)/utils/core_log.c \
	$(CORE_DIR)/utils/core_string.c \
	$(CORE_DIR)/utils/core_sha256.c \
	$(CORE_DIR)/core_aes.c \
	$(PORTFILES_DIR)/aiot_port/posix_port.c \
#	$(EXTERN_DIR)/library/ssl_tls.c \
	$(EXTERN_DIR)/library/x509_crt.c \
	$(EXTERN_DIR)/library/md.c \
	$(EXTERN_DIR)/library/pk.c \
	$(EXTERN_DIR)/library/debug.c \
	$(EXTERN_DIR)/library/platform_util.c \
	$(EXTERN_DIR)/library/cipher.c \
	$(EXTERN_DIR)/library/platform.c \
	$(EXTERN_DIR)/library/pkparse.c \
	$(EXTERN_DIR)/library/ssl_ciphersuites.c \
	$(EXTERN_DIR)/library/sha256.c \
	$(EXTERN_DIR)/library/sha512.c \

# Additional source files from another directory
OTHER_SRC_FILES = $(shell find $(EXTERN_DIR) -type f -name '*.c')

# Combine the source files
SRC_FILES += $(OTHER_SRC_FILES)

# 定义输出目标
OUTPUT = output

# 默认目标，编译输出目标
all: $(OUTPUT)

# 编译命令
$(OUTPUT): $(SRC_FILES)
	$(CC) $(CFLAGS) $(INCLUDE_DIRS) $^ -o $@

# 清理目标，删除输出文件
clean:
	rm -f $(OUTPUT)