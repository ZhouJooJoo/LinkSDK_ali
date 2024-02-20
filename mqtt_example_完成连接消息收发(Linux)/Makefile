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
    $(SRC_DIR)/mqtt_hangxin.c \
    $(CORE_DIR)/aiot_mqtt_api.c \
    $(CORE_DIR)/aiot_state_api.c \
    $(SYSDEP_DIR)/core_sysdep.c \
    $(PORTFILES_DIR)/aiot_port/posix_port.c \
    $(UTILS_DIR)/core_log.c \
    $(UTILS_DIR)/core_diag.c \
    $(UTILS_DIR)/core_string.c \
    $(UTILS_DIR)/core_global.c \
    $(UTILS_DIR)/core_auth.c \
    $(SYSDEP_DIR)/core_adapter.c \
    $(UTILS_DIR)/core_sha256.c   \
    $(EXTERN_DIR)/library/ssl_tls.c \
    $(EXTERN_DIR)/library/x509_crt.c \
    $(EXTERN_DIR)/library/pk.c \
    $(EXTERN_DIR)/library/pkparse.c \
    $(EXTERN_DIR)/library/debug.c \
    $(EXTERN_DIR)/library/platform.c \
    $(EXTERN_DIR)/library/md.c \
    $(EXTERN_DIR)/library/platform_util.c \
    $(EXTERN_DIR)/library/cipher.c \
    $(EXTERN_DIR)/library/sha256.c \
    $(EXTERN_DIR)/library/ssl_ciphersuites.c \
    $(EXTERN_DIR)/library/ssl_cli.c \
    $(EXTERN_DIR)/library/asn1parse.c \
    $(EXTERN_DIR)/library/x509.c \
    $(EXTERN_DIR)/library/pem.c \
    $(EXTERN_DIR)/library/oid.c \
    $(EXTERN_DIR)/library/rsa.c \
    $(EXTERN_DIR)/library/bignum.c \
    $(EXTERN_DIR)/library/pk_wrap.c \
    $(EXTERN_DIR)/library/md_wrap.c \
    $(EXTERN_DIR)/library/cipher_wrap.c \
    $(EXTERN_DIR)/library/base64.c \
    $(EXTERN_DIR)/library/rsa_internal.c \
    $(EXTERN_DIR)/library/sha1.c \
    $(EXTERN_DIR)/library/aes.c \


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