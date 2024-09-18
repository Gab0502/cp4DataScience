## Gêneros Relacionados ao Horror

### Análise de Gêneros Mais Correlacionados com "Horror"

**Subtítulo:** Utilizando dados do Netflix, Rotten Tomatoes e IMDb

### Descrição
A análise foi conduzida para identificar quais gêneros de filmes estão mais frequentemente associados ao gênero "Horror" nas plataformas Netflix, Rotten Tomatoes e IMDb. A combinação de dados dessas três plataformas permitiu uma análise mais ampla e detalhada dos padrões de gêneros nos filmes de horror.

### Código Usado para a Análise

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from collections import Counter

# Sample Data Loading (Assuming 'horror_df' is already available as explained)
# Here, I am using a mock of the DataFrame structure to perform the required steps

# Sample 'horror_df' columns available in the dataset
# Mocking this structure for explanation purposes
data = {
    'genres_netflix': [['Horror', 'Mystery & Suspense'], ['Action & Adventure', 'Horror', 'Mystery & Suspense'],
                       ['Drama', 'Horror', 'Mystery & Suspense']],
    'genres_rotten': [['Horror', 'Thriller'], ['Horror', 'Mystery'], ['Drama', 'Horror', 'Thriller']],
    'genres': [['Horror', 'Thriller'], ['Action & Adventure', 'Horror'], ['Horror', 'Comedy']]
}

horror_df = pd.DataFrame(data)

# Combine genres from different sources if available
if 'genres_netflix' in horror_df.columns and 'genres_rotten' in horror_df.columns:
    horror_df['all_genres'] = horror_df['genres_netflix'] + horror_df['genres_rotten']
elif 'genres' in horror_df.columns:
    horror_df['all_genres'] = horror_df['genres'].str.split(',')
else:
    print("Nenhuma coluna de gêneros disponível para combinar. Verifique os dados.")

# Example data in 'all_genres'
print("Exemplo de dados em 'all_genres':", horror_df['all_genres'].head())

# If 'all_genres' is successfully created
if 'all_genres' in horror_df.columns:
    # Remove 'Horror' from genre lists
    horror_df['genres_without_horror'] = horror_df['all_genres'].apply(lambda x: [genre.strip() for genre in x if 'Horror' not in genre])

    # Count occurrences of all genres except 'Horror'
    all_genres = [genre for sublist in horror_df['genres_without_horror'] for genre in sublist]
    genre_counts = Counter(all_genres)

    # Create DataFrame of genre counts
    genre_df = pd.DataFrame(genre_counts.items(), columns=['Genre', 'Count'])

    # Filter out 'Horror' from the results
    genre_df = genre_df[~genre_df['Genre'].str.contains('Horror', case=False, na=False)]

    # Sort genres by count
    genre_df = genre_df.sort_values(by='Count', ascending=False)

    # Plot the most correlated genres with 'Horror'
    plt.figure(figsize=(12, 8))
    sns.barplot(x='Count', y='Genre', data=genre_df, palette='viridis')
    plt.title('Gêneros Correlacionados com Horror (Netflix + Rotten Tomatoes + IMDb)')
    plt.xlabel('Contagem')
    plt.ylabel('Gênero')
    plt.show()
else:
    print("Não foi possível criar a coluna 'all_genres'. Verifique os dados.")
