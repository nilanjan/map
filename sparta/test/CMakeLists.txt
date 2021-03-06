PROJECT (SPARTA_TESTS)

# Enable testing
enable_testing ()

# Setup options for valgrind testing.
set (VALGRIND_OPTS "--error-exitcode=5 \
      --leak-check=full \
      --show-reachable=yes \
      --undef-value-errors=yes \
      --suppressions=${SPARTA_BASE}/test/valgrind_leakcheck.supp \
      --soname-synonyms=somalloc=NONE")
set (VALGRIND_TEST_LABEL valgrind_test)

# Add the custom regress/regress_valgrind targets.
add_custom_target (regress)
add_custom_target (regress_valgrind)

# NOTE:
# running ctest with --test-action test creates Testing/<datetime>/Test.xml
# that can be loaded into the CI test result tracker
add_custom_command (TARGET regress          POST_BUILD COMMAND ctest -LE ${VALGRIND_TEST_LABEL} -j10 --test-action test)
add_custom_command (TARGET regress_valgrind POST_BUILD COMMAND ctest -L  ${VALGRIND_TEST_LABEL} -j10 --test-action test)

#add_subdirectory (pipeViewer)
add_subdirectory (Array)
add_subdirectory (Audience)
add_subdirectory (Buffer)
add_subdirectory (Bus)
add_subdirectory (cache)
add_subdirectory (Clock)
add_subdirectory (CircularBuffer)
add_subdirectory (Color)
add_subdirectory (CommandLineSimulator)
add_subdirectory (Counter)
add_subdirectory (ContextCounter)
add_subdirectory (CycleHistogram)
add_subdirectory (DAG)
add_subdirectory (DAG_Ordering)
add_subdirectory (DataView)
add_subdirectory (Enum)
add_subdirectory (Events)
add_subdirectory (FastCheckpoint)
add_subdirectory (KeyPairCollect)
add_subdirectory (KeyValue)
add_subdirectory (Log)
add_subdirectory (LogAll)
add_subdirectory (Memory)
add_subdirectory (MemoryMap)
add_subdirectory (MethodDelegate)
add_subdirectory (Monitor)
add_subdirectory (Parameter)
add_subdirectory (PEvents)
add_subdirectory (Pipe)
add_subdirectory (Preloading)
add_subdirectory (Pipeline)
add_subdirectory (Port)
add_subdirectory (Queue)
add_subdirectory (Rational)
add_subdirectory (SpartaSharedPointer)
add_subdirectory (Register)
add_subdirectory (Report)
add_subdirectory (ReportVerifier)
add_subdirectory (ResourceAssert)
add_subdirectory (SpartaException)
add_subdirectory (Scheduler)
add_subdirectory (SharedData)
add_subdirectory (SimDB)
add_subdirectory (SmartLexCast)
add_subdirectory (State)
add_subdirectory (StaticInit)
add_subdirectory (Statistic)
add_subdirectory (StatisticExpression)
add_subdirectory (SyncPort)
add_subdirectory (Tag)
add_subdirectory (TreeFilter)
add_subdirectory (TreeNode)
add_subdirectory (TreeNodePrivacy)
add_subdirectory (TreeNodeScope)
add_subdirectory (TreeNodeDebug)
add_subdirectory (Trigger)
add_subdirectory (VirtualParameterTree)
add_subdirectory (HierarchicalBuilding)
add_subdirectory (Notification)
add_subdirectory (MirrorNotification)
add_subdirectory (Utils)
add_subdirectory (BitArray)
add_subdirectory (StateTimer)
add_subdirectory (ValidValue)
add_subdirectory (PairCollector)
add_subdirectory (NestedPEvents)
add_subdirectory (StateResidencyTracker)
add_subdirectory (MetaTypeList)
add_subdirectory (LockedValue)
add_subdirectory (EnumCycleHistogram)
