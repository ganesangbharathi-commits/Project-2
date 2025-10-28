

def get_posts():
    response = requests.get('https://jsonplaceholder.typicode.com/posts')
    return response.json()

def get_post(post_id):
    response = requests.get(f'https://jsonplaceholder.typicode.com/posts/{post_id}')
    return response.json()

def main():
    print("JSONPlaceholder API CLI")
    print("------------------------")

    while True:
        print("1. Get all posts")
        print("2. Get a post by ID")
        print("3. Quit")

        choice = input("Choose an option: ")

        if choice == "1":
            posts = get_posts()
            print(json.dumps(posts, indent=4))
        elif choice == "2":
            post_id = input("Enter post ID: ")
            post = get_post(post_id)
            print(json.dumps(post, indent=4))
        elif choice == "3":
            break
        else:
            print("Invalid option. Please choose again.")

if __name__ == "__main__":
    main()
