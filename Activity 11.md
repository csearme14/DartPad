# DartPad
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: MyApp(),
  ));
}

class MyApp extends StatefulWidget {
  @override
  _State createState() => _State();
}

class _State extends State<MyApp> {
  final GlobalKey<ScaffoldState> _scaffoldKey = new GlobalKey<ScaffoldState>();

  void _showMessageInScaffold(String message){
    try {
      _scaffoldKey.currentState.showSnackBar(
          SnackBar(
            content: Text(message),
            action: SnackBarAction(
              label: 'Undo',
              onPressed: () {
                // some code
                print('Action in Snackbar has been pressed.');
              },
            ),
          )
      );
    } on Exception catch (e, s) {
      print(s);
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        key: _scaffoldKey,
        appBar: AppBar(
          title: Text('Checkponit2 page'),
        ),
        body: Center(

        child: Container(
        height: 100.0,
        width: 150.0,

        
            child: OutlineButton(

              textColor: Colors.red,
              color: Colors.lightGreen,
              borderSide: BorderSide(color: Colors.black, width: 1.0, style: BorderStyle.solid),
              child: Text('Press this button'),

              onPressed: (){
                _showMessageInScaffold("Chalisa Sinban 6135512020");
              },
            )
        )
        )
    );
  }
}
