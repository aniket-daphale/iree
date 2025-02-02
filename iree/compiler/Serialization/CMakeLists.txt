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
    Serialization
  HDRS
    "BytecodeTables.h"
    "BytecodeWriter.h"
    "VMDeviceTableBuilder.h"
    "VMExecutableTableBuilder.h"
    "VMFunctionBuilder.h"
    "VMFunctionTableBuilder.h"
    "VMModuleBuilder.h"
    "VMSourceMapBuilder.h"
  SRCS
    "BytecodeTables.cpp"
    "BytecodeWriter.cpp"
    "VMDeviceTableBuilder.cpp"
    "VMExecutableTableBuilder.cpp"
    "VMFunctionBuilder.cpp"
    "VMFunctionTableBuilder.cpp"
    "VMModuleBuilder.cpp"
    "VMSourceMapBuilder.cpp"
  DEPS
    iree::compiler::IR
    iree::compiler::IR::Interpreter
    iree::compiler::IR::Sequencer
    iree::schemas
    iree::schemas::bytecode::interpreter_bytecode_v0
    iree::schemas::bytecode::sequencer_bytecode_v0
    LLVMSupport
    MLIRIR
  PUBLIC
)
