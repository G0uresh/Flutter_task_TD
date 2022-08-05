# Coding Questions

Question 1

<img width="648" alt="Screenshot 2022-08-05 at 11 52 32 AM" src="https://user-images.githubusercontent.com/25320909/183014474-d05b86ff-3984-46bf-9837-e3e77a622536.png">

solution : 

<img width="878" alt="Screenshot 2022-08-05 at 12 53 12 AM" src="https://user-images.githubusercontent.com/25320909/183014497-2e51bf78-f656-42f0-a676-4fc8bc0e3fa3.png">


2. Write a function to call the below mentioned API and parse the data. Make sure
the function return an object of News item, which contains News article Title,
News article Content, Date of News Published, Banner Image of News article.
https://inshorts.deta.dev/news?category=all


````
```

 Future<NewsModel> fetchNews() async {
    final response = await http
        .get(Uri.parse('https://inshorts.deta.dev/news?category=all'));

    if (response.statusCode == 200) {
      Map<String, dynamic> res = jsonDecode(response.body);
      return NewsModel.fromJson(res);
    } else {
      throw Exception('Failed to load');
    }
  }
}

class NewsModel {
  List<NewsItemModel?>? articles;
  String category;

  NewsModel({
    required this.category,
    required this.articles,
  });

  factory NewsModel.fromJson(Map<String, dynamic> json) {
    List list = json['data'];
    List<NewsItemModel> articles =
        list.map((e) => NewsItemModel.fromJson(e)).toList();
    return NewsModel(
      category: json['category'] ?? '',
      articles: articles,
    );
  }
}

class NewsItemModel {
  String id;
  String title;
  String? readMoreUrl;
  String urlToImage;
  String? url;
  String date;
  String time;
  String content;

  NewsItemModel({
    required this.id,
    required this.title,
    this.readMoreUrl,
    required this.urlToImage,
    this.url,
    required this.date,
    required this.time,
    required this.content,
  });

  factory NewsItemModel.fromJson(Map<String, dynamic> json) {
    return NewsItemModel(
      id: json['id'],
      title: json['title'] ?? '',
      readMoreUrl: json['readMoreUrl'] ?? '',
      urlToImage: json['imageUrl'] ?? '',
      url: json['url'] ?? '',
      date: json['date'] ?? '',
      time: json['time'] ?? '',
      content: json['content'] ?? '',
    );
  }
  
```
````

Question 3 :

<img width="648" alt="Screenshot 2022-08-05 at 11 57 51 AM" src="https://user-images.githubusercontent.com/25320909/183015311-eb047f55-ba22-4e9c-b03e-6a932d3dd4ec.png">

1. The method name should start with lowerCamelCase (Best practice)
2. No issue found .The counting variable will always return  1000000000 regardless of initial values of i and counting variable.
3. We can also use while loop and eliminate creating extra variable

