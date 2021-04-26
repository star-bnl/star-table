cmake_minimum_required(VERSION 3.6 FATAL_ERROR)

project(star-ttable LANGUAGES CXX)

# By default build shared libraries
OPTION(BUILD_SHARED_LIBS "Global flag to cause add_library to create shared libraries if on" ON)

find_package(ROOT REQUIRED)

add_library(Table
  src/TCernLib.cxx
  src/TChair.cxx
  src/TColumnView.cxx
  src/TDataSet.cxx
  src/TDataSetIter.cxx
  src/TDsKey.cxx
  src/TFileIter.cxx
  src/TFileSet.cxx
  src/TGenericTable.cxx
  src/TIndexTable.cxx
  src/TObjectSet.cxx
  src/TPoints3D.cxx
  src/TPointsArray3D.cxx
  src/TPolyLineShape.cxx
  src/TResponseTable.cxx
  src/TTable3Points.cxx
  src/TTable.cxx
  src/TTableDescriptor.cxx
  src/TTableIter.cxx
  src/TTableMap.cxx
  src/TTablePadView3D.cxx
  src/TTablePoints.cxx
  src/TTableSorter.cxx
  src/TVolume.cxx
  src/TVolumePosition.cxx
  src/TVolumeView.cxx
  src/TVolumeViewIter.cxx
)

target_include_directories(Table PRIVATE include/)

target_link_libraries(Table
  ROOT::Core
  ROOT::Tree
  ROOT::Gpad
  ROOT::Graf3d
  ROOT::Graf
  ROOT::Hist
  ROOT::RIO
  ROOT::MathCore
)

install(TARGETS Table)
install(DIRECTORY include/ TYPE INCLUDE)
