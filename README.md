# Instagram Feed UI

A new Flutter project.

## Getting Started

<pre>
import 'package:flutter/material.dart';

void main() {
  runApp(Myappp());
}

class Myappp extends StatelessWidget {
  const Myappp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Instagramfeed(),
    );
  }
}

class Instagramfeed extends StatelessWidget {
  const Instagramfeed({super.key});

  final List<String> posts = const [
    "Post1",
    "Post2",
    "Post3",
    "Post4",
    "Post5",
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: CircleAvatar(
          child: Image.asset(
            "asset/logo.png",
            height: 40,
            width: 40,
          ),
        ),
        title: Text("MeetSoc Feed", textAlign: TextAlign.center),
        actions: [
          IconButton(onPressed: () {}, icon: Icon(Icons.add, size: 40)),
        ],
      ),
      body: Column(
        children: [
          Expanded(
            child: ListView.builder(
              itemCount: posts.length,
              itemBuilder: (context, index) {
                return Column(
                  children: [
                    ListTile(
                      leading: CircleAvatar(
                        backgroundImage: NetworkImage(
                          'https://picsum.photos/200',
                        ),
                      ),
                      title: Row(
                        children: [
                          const Text(
                            "Adnan Khan",
                            style: TextStyle(fontWeight: FontWeight.bold
                            ,fontSize: 20),
                          ),
                          const SizedBox(width: 5),
                          // নাম এবং টিকের মাঝে অল্প ফাঁকা
                          const Icon(
                            Icons.verified,
                            color: Colors.blue,
                            size: 16, // আইকনটি ছোট রাখতে ১৬ বা ১৮ সাইজ ভালো
                          ),
                        ],
                      ),
                      subtitle: Text("Dhaka, Bangladesh"),
                      trailing: Icon(Icons.more_vert),
                    ),
                    Image.network(
                      'https://picsum.photos/200',
                      fit: BoxFit.cover,
                      height: 350,
                      width: double.infinity,
                    ),
                    Row(
                      children: [
                        IconButton(
                          onPressed: () {},
                          icon: Icon(Icons.favorite_border),
                        ),
                        IconButton(
                          onPressed: () {},
                          icon: Icon(Icons.comment_outlined),
                        ),
                        IconButton(onPressed: () {}, icon: Icon(Icons.share)),
                        const Spacer(),
                        IconButton(
                          onPressed: () {},
                          icon: Icon(Icons.bookmark_border),
                        ),
                        const Divider(height: 1, thickness: 0.5),
                        // প্রতিটি পোস্টের নিচে চিকন একটি বর্ডার
                        const SizedBox(height: 10),
                        // একটু গ্যাপ
                      ],
                    ),
                  ],
                );
              },
            ),
          ),
        ],
      ),
    );
  }
}

</pre>
