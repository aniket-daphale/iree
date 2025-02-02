# Copyright 2019 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

iree_cc_library(
  NAME
    Sequencer
  HDRS
    "HLDialect.h"
    "HLOps.h"
    "HLOps.h.inc"
    "LLDialect.h"
    "LLOps.h"
    "LLOps.h.inc"
    "OpWriters.h"
  SRCS
    "HLDialect.cpp"
    "HLOps.cpp"
    "HLOps.cpp.inc"
    "LLDialect.cpp"
    "LLOps.cpp"
    "LLOps.cpp.inc"
    "OpWriters.cpp"
  DEPS
    iree::compiler::IR
    iree::compiler::IR::Sequencer::HLOpsGen
    iree::compiler::IR::Sequencer::LLOpsGen
    iree::compiler::Serialization
    iree::compiler::Utils
    LLVMSupport
    MLIRIR
  ALWAYSLINK
  PUBLIC
)

iree_tablegen_library(
  NAME
    HLOpsGen
  SRCS
    HLOps.td
  OUTS
    -gen-op-decls HLOps.h.inc
    -gen-op-defs HLOps.cpp.inc
)

iree_tablegen_library(
  NAME
    LLOpsGen
  SRCS
    LLOps.td
  OUTS
    -gen-op-decls LLOps.h.inc
    -gen-op-defs LLOps.cpp.inc
)
