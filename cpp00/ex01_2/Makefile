NAME = phonebook
CC = c++
CFLAGS = -Wall -Wextra -Werror -std=c++98
REMOVE = rm -rf
SAFE_MKDIR = mkdir -p
SOURCES_PATH = $(PWD)
INCLUDES_PATH = $(PWD)

SOURCE_FILES = $(shell ls ./ | grep .cpp$)
SOURCES = $(addprefix $(SOURCES_PATH)/,$(SOURCE_FILES))
OBJECTS = ${SOURCES:.cpp=.o}

.PHONY: all re clean fclean

all: $(NAME)

$(NAME): $(OBJECTS)
	@$(CC) $(CFLAGS) $(OBJECTS) -o $(NAME)

$(SOURCES_PATH)/%.o: $(SOURCES_PATH)/%.cpp Phonebook.hpp Contact.hpp
	@$(CC) $(CFLAGS) -I$(INCLUDES_PATH) -o $@ -c $<

re: fclean all

clean:
	@$(REMOVE) $(OBJECTS)

fclean: clean
	@$(REMOVE) $(NAME)
