# codsoft-ai-task-3
# Recommendation system acc to user prefernce
data = [
    {'Title': 'Movie A', 'Genre': 'Action', 'Rating': 5},
    {'Title': 'Movie B', 'Genre': 'Romance', 'Rating': 4},
    {'Title': 'Movie C', 'Genre': 'Action', 'Rating': 3},
    {'Title': 'Book D', 'Genre': 'Thriller', 'Rating': 4},
    {'Title': 'Book E', 'Genre': 'Romance', 'Rating': 2},
    {'Title': 'Movie F', 'Genre': 'Action', 'Rating': 4},
    {'Title': 'Book G', 'Genre': 'Sci-Fi', 'Rating': 3},
]


def recommend_items(user_preferences, data, top_n=3):
   
    recommended = []

    for item in data:
        if item['Genre'] in user_preferences:
            recommended.append(item)

  
    recommended.sort(key=lambda x: x['Rating'], reverse=True)


    return recommended[:top_n]


user_preferences = ['Action', 'Romance']


recommended_items = recommend_items(user_preferences, data)


print("Recommended Items:")
for item in recommended_items:
    print(f"{item['Title']} - Genre: {item['Genre']}, Rating: {item['Rating']}")
