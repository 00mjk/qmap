pybind11_add_module(py${PROJECT_NAME} bindings.cpp)
target_link_libraries(py${PROJECT_NAME} PUBLIC ${PROJECT_NAME}_heuristic_lib MQT::qfr_python
                                               pybind11_json)
target_compile_definitions(py${PROJECT_NAME} PUBLIC Z3_FOUND)
target_link_libraries(py${PROJECT_NAME} PUBLIC ${PROJECT_NAME}_exact_lib)
target_link_libraries(py${PROJECT_NAME} PUBLIC ${PROJECT_NAME}_cliffordsynthesis_lib)
target_compile_definitions(py${PROJECT_NAME} PRIVATE VERSION_INFO=${QMAP_VERSION_INFO})
