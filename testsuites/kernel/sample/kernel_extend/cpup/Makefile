
include $(LITEOSTESTTOPDIR)/config.mk

MODULE_NAME := cpuptest

LOCAL_INCLUDE := \
    -I $(LITEOSTESTTOPDIR)/kernel/include \
    -I $(LITEOSTESTTOPDIR)/kernel/sample/kernel_extend/cpup \
    -I $(LITEOSTOPDIR)/kernel/extended/include/

SRC_MODULES := .

ifeq ($(LOSCFG_KERNEL_SMP), y)
SMP_MODULES := smp
endif

ifeq ($(LOSCFG_TEST_LLT), y)
LLT_MODULES := llt
endif

ifeq ($(LOSCFG_TEST_PRESSURE), y)
PRESSURE_MODULES := pressure
endif

ifeq ($(LOSCFG_TEST_SMOKE), y)
SMOKE_MODULES := smoke
endif

ifeq ($(LOSCFG_TEST_FULL), y)
FULL_MODULES := full
endif

LOCAL_MODULES := $(SRC_MODULES) $(SMOKE_MODULES) $(FULL_MODULES) $(SMP_MODULES) $(LLT_MODULES)

LOCAL_SRCS := $(foreach dir,$(LOCAL_MODULES),$(wildcard $(dir)/*.c))
LOCAL_CHS := $(foreach dir,$(LOCAL_MODULES),$(wildcard $(dir)/*.h))

LOCAL_FLAGS :=  $(LOCAL_INCLUDE)  -Wno-error

include $(MODULE)
