# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: rbroque <rbroque@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2022/07/16 12:57:35 by rbroque           #+#    #+#              #
#    Updated: 2022/07/23 22:07:17 by rbroque          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = rush-02

### SRCS

PATH_SRCS = srcs

SRCS += string.c
SRCS += ft_atou.c
SRCS += print_nb.c
SRCS += print.c
SRCS += ft_split.c
SRCS += parsing.c
SRCS += lexer.c
SRCS += map.c
SRCS += read_file.c
SRCS += free.c
SRCS += rush02.c

vpath %.c $(PATH_SRCS)

### OBJS

PATH_OBJS = objs

OBJS = $(patsubst %.c, $(PATH_OBJS)/%.o, $(SRCS))

### INCLUDES

INCLUDES = includes/

HEADER += rush02.h

vpath %.h $(INCLUDES)

### COMPILATION

CC = gcc
CFLAGS += -Wall
CFLAGS += -Wextra
CFLAGS += -Werror

ifeq ($(debug), true)
	CFLAGS += -g3
	CFLAGS += -fsanitize=address,undefined
endif

### RULES

all: $(NAME)

$(NAME): $(OBJS)
	$(CC) $(CFLAGS) $^ -o $@ -I $(INCLUDES)

$(OBJS): $(PATH_OBJS)/%.o: %.c $(HEADER)
	mkdir -p $(PATH_OBJS)
	$(CC) $(CFLAGS) -c $< -o $@ -I $(INCLUDES)

clean:
	$(RM) -R $(PATH_OBJS)

fclean: clean
	$(RM) $(NAME)

re: fclean
	$(MAKE)

.PHONY: all clean fclean re
