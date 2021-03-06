cmake_minimum_required(VERSION 3.3)
project(final-project CXX)
include(.cs211/cmake/CMakeLists.txt)

set(MODEL_SRC
        # LIST ADDITIONAL MODEL .cxx FILES HERE:
        src/missile.cxx
        src/geometry.cxx
        src/screenObject.cxx
        src/falcon.cxx
        src/asteroid.cxx
        src/destroyer.cxx
        src/deathStar.cxx
        src/model.cxx)

add_program(main
    src/main.cxx
    src/ui.cxx
    # LIST ADDITIONAL NON-MODEL (UI) .cxx FILES HERE:
    ${MODEL_SRC})
target_link_libraries(main ge211)

add_test_program(model_test
    test/model_test.cxx
    ${MODEL_SRC})
target_link_libraries(model_test ge211)

add_test_program(screenObject_test
        test/screenObject_test.cxx
        ${MODEL_SRC})
target_link_libraries(screenObject_test ge211)

add_test_program(missile_test
        test/missile_test.cxx
        ${MODEL_SRC})
target_link_libraries(missile_test ge211)
