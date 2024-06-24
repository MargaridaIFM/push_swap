NAME = push_swap
CC = cc
FLAGS = -Wall -Werror -Wextra -g #-fsanitize=address 
LIBC = ar rcs
LIBFT = $(LIBFTDIR)/libft.a
LIBFTDIR =./libft
RM = rm -f

SRCS = 	push_swap.c \
		aux_functions.c \
		check_input.c \
		parsing.c \
		add_arguments.c \
		swap.c \
		rotate.c \
		reverse.c \
		push.c \
		sorting.c \
		sort_5.c \
		sort_algorithm.c \
		sort_aux.c \
		sort_aux2.c \
		test_list_functions.c \

OBJDIR = ./objs
OBJS = $(addprefix $(OBJDIR)/, $(SRCS:.c=.o))

$(OBJDIR)/%.o: %.c
	@mkdir -p $(OBJDIR)
	@$(CC) $(FLAGS) -c $< -o $@

all:$(NAME)

$(NAME) : $(LIBFT) $(OBJS)
	@$(CC) $(FLAGS) $(OBJS) $(LIBFT) -o $(NAME)
	@echo $(NAME) compiled

$(LIBFT):
	@echo libft compiling...
	@$(MAKE) -C $(LIBFTDIR) --no-print-directory
	@echo libft compiled
	
clean:
	@$(MAKE) clean -C $(LIBFTDIR) --no-print-directory
	@$(RM) $(OBJS)

fclean:	clean
	@$(MAKE) fclean -C $(LIBFTDIR) --no-print-directory
	@$(RM) $(NAME)

re:	fclean all

x: 
	 make re && valgrind --leak-check=full ./push_swap 1 34k5 3 66 

.PHONY:		all clean fclean re