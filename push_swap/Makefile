# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: rbattal <rbattal@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/06/10 02:22:41 by rbattal           #+#    #+#              #
#    Updated: 2023/06/10 02:24:07 by rbattal          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #


NAME = push_swap

LIBFT = libft

LIBFTM = libft/libft.a

CC = gcc

CFLAGS = -Wall -Wextra -Werror

CFILES_1 = push_swap.c

CFILES_2 = function.c \
			function2.c \
			function3.c \
			rules_a.c \
			rules_b.c \
			rules_2.c


OBJS_1 = $(CFILES_1:.c=.o)

OBJS_2 = $(CFILES_2:.c=.o)



$(NAME): $(OBJS_1) $(OBJS_2)
	@make -C $(LIBFT)
	@$(CC) $(CFLAGS) $(OBJS_1) $(OBJS_2) $(LIBFTM) -o $(NAME)
	@echo "\nPush_swap is ready\n"


all: $(NAME) $(BONUS_NAME)
	@echo "\nll files compiled\n"
	

clean:
		@rm -f $(OBJS_1) $(OBJS_2)
		@make clean -C $(LIBFT)
		@echo "\nObjects files deleted\n"

fclean: clean
		@make fclean -C $(LIBFT)
		@rm -rf $(NAME)
		@echo "\nArchive file deleted\n"

re: fclean all