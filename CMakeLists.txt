# ---------------------------------------------------------------------------
# Licensed to the Apache Software Foundation (ASF) under one or more
# contributor license agreements.  See the NOTICE file distributed with
# this work for additional information regarding copyright ownership.
# The ASF licenses this file to You under the Apache License, Version 2.0
# (the "License"); you may not use this file except in compliance with
# the License.  You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ---------------------------------------------------------------------------

CMAKE_MINIMUM_REQUIRED(VERSION 2.8 FATAL_ERROR)

PROJECT(uimacpp_ros)

FIND_PACKAGE(catkin REQUIRED)

ADD_DEFINITIONS(-DUIMA_VERSION=2.4.1)

LIST(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")

# Set exported headers and libs
catkin_package(
  INCLUDE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}/src/cas/include ${CMAKE_CURRENT_SOURCE_DIR}/src/framework/include ${CMAKE_CURRENT_SOURCE_DIR}/src/jni/include
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS
  DEPENDS XercesC APR JNI)

ADD_SUBDIRECTORY(src)
