find_package(SFML REQUIRED COMPONENTS system window graphics)
FIND_PACKAGE(Boost REQUIRED COMPONENTS system thread)

include_directories(
    ${SFML_INCLUDE_DIR}
    ${Boost_INCLUDE_DIR}
)

link_directories(
    ${Boost_LIBRARY_DIRS}
)

set(Engine_SOURCES
    Engine.hpp
    Engine.cpp

    Resources.hpp
    Resources.cpp

    SpriteSheet.hpp
    SpriteSheet.cpp

    DataFile.hpp
    DataFile.cpp
)

set(Game_SOURCES
    Game/Menu.hpp
    Game/Menu.cpp

    Game/Countdown.hpp
    Game/Countdown.cpp

    Game/World.hpp
    Game/World.cpp

    Game/Player.hpp
    Game/Player.cpp

    Game/Weapon.hpp
    Game/Weapon.cpp

    Game/Enemy.hpp
    Game/Enemy.cpp
)

source_group(Engine FILES ${Engine_SOURCES})
source_group(Game FILES ${Game_SOURCES})

add_executable(LD28 main.cpp ${Engine_SOURCES} ${Game_SOURCES})
target_link_libraries(LD28 Kunlaboro ${SFML_LIBRARIES})