# flutter
sign up basic
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      debugShowCheckedModeBanner: false,
      home: const MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final _formkey = GlobalKey<FormState>();
  Size? size;
  final TextEditingController _nameControlller = TextEditingController();
  final TextEditingController _lastControlller = TextEditingController();
  final TextEditingController _nmControlller = TextEditingController();
  bool isView = false;

  void initSate() {
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    size = MediaQuery.of(context).size;
    return Scaffold(
      backgroundColor: Colors.white54,
      appBar: AppBar(
        title: const Text("First page"),
        titleTextStyle: const TextStyle(color: Colors.deepOrange, fontSize: 30),
      ),
      body: SingleChildScrollView(
        scrollDirection: Axis.vertical,
        child: Padding(
          padding: const EdgeInsets.all(8),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            crossAxisAlignment: CrossAxisAlignment.center,
            mainAxisSize: MainAxisSize.min,
            children: [
              SizedBox(height:300),
              Image.asset("assets/images/download-button-png.png", height: 200,),
              const Text(
                "Sign up",
                style: TextStyle(fontSize: 24),
              ),
              Padding(
                padding: const EdgeInsets.all(8.0),
                child: Form(
                  key: _formkey,
                  child: Column(
                    crossAxisAlignment: CrossAxisAlignment.center,
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                      Row(
                        mainAxisSize: MainAxisSize.min,
                        crossAxisAlignment: CrossAxisAlignment.center,
                        children: [
                          const Icon(Icons.person, size: 30, color: Colors.black54),
                          SizedBox(
                            width: size!.width * 0.6,
                            child: Padding(
                              padding: const EdgeInsets.all(8.0),
                              child: TextFormField(
                                controller: _nameControlller,
                                decoration: const InputDecoration(
                                  hintText: "Enter full name",
                                  hintStyle: TextStyle(color: Colors.black45),
                                  border: UnderlineInputBorder(),
                                ),
                                keyboardType: TextInputType.name,
                                validator: (value) {
                                  if (value == null || value.isEmpty) {
                                    return "Please enter some text";
                                  }
                                  return null;
                                },
                              ),
                            ),
                          ),
                        ],
                      ),
                      SizedBox(height: 20),
                      Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        crossAxisAlignment: CrossAxisAlignment.center,
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          const Icon(Icons.g_mobiledata_outlined),
                          SizedBox(
                            width: size!.width * 0.6,
                            child: Padding(
                              padding: const EdgeInsets.all(8),
                              child: TextFormField(
                                controller: _lastControlller,
                                decoration: InputDecoration(
                                  hintText: "Enter correct gmail",
                                  hintStyle: TextStyle(color: Colors.black45),
                                  border: UnderlineInputBorder(),
                                ),
                                keyboardType: TextInputType.emailAddress,
                                validator: (value){
                                  if(value==null||value.isEmpty){
                                    return "Enter some text";
                                  }
                                  return null;
                                },
                              ),
                            ),
                          ),
                        ],

                      ),
                      SizedBox(height: 20),
                      Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        crossAxisAlignment: CrossAxisAlignment.center,
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          const Icon(Icons.phone,size: 24),
                          SizedBox(
                            width: size!.width * 0.6,
                            child: Padding(
                              padding: const EdgeInsets.all(8),
                              child: TextFormField(
                                controller: _nmControlller,
                                decoration: InputDecoration(
                                  hintText: "Enter correct gmail",
                                  hintStyle: TextStyle(color: Colors.black45),
                                  border: UnderlineInputBorder(),
                                ),
                                keyboardType: TextInputType.phone,
                                validator: (value){
                                  if(value==null||value.isEmpty){
                                    return "Enter some text";
                                  }
                                  return null;
                                },
                              ),
                            ),
                          ),
                        ],
                      ),
                      SizedBox(
                        width:size!.width * 0.6,
                        child: ElevatedButton(
                          style: ButtonStyle(
                            backgroundColor: WidgetStatePropertyAll(Colors.blueAccent),
                          ),
                            onPressed: () {
                            },
                            child: Text("Continue"),

                        ),

                      ),
                    ],
                  ),
                ),
              ),
            ],
          ),
        ),
      ),

    );
  }
}
