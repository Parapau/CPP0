# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: pafranco <pafranco@student.42barcelon      +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2025/07/02 12:53:07 by pafranco          #+#    #+#              #
#    Updated: 2025/07/21 19:04:04 by pafranco         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME		= PhoneBook
	
CC			= c++
FLAGS		= -Wall -Wextra -Werror -g -std=c++98
RM			= rm -rf

SRCDIR = 	src/
OBJDIR = 	obj/

FILES		= main Contact PhoneBook

SRC			= $(addprefix $(SRCDIR), $(FILES:=.cpp))
OBJ			= $(addprefix $(OBJDIR), $(FILES:=.o))
DEPS		= $(addprefix $(OBJDIR), $(FILES:=.d))
HEADER		= Contact.hpp PhoneBook.hpp

all: $(NAME)

$(NAME): $(OBJ) $(HEADER)
	@$(CC) $(OBJ) -o $(NAME)
	@printf " - Executable ready.\n"

$(OBJDIR)%.o: $(SRCDIR)%.cpp $(HEADER) Makefile
	@mkdir -p $(OBJDIR)
	@$(CC) $(FLAGS) -c -MMD $< -o $@

clean:
	@$(RM) $(OBJDIR) $(OBJ)
	@printf " - Object files removed.\n"

fclean: clean
	@$(RM) $(NAME)
	@printf " - Executable removed.\n"

re: fclean all

-include $(DEPS)

.PHONY: all clean fclean re
