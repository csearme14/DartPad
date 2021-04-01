# DartPad
import "package:flutter/material.dart";
void main() => runApp(MyApp());
class MyApp extends StatefulWidget {
  MyApp({Key key}) : super(key : key);
  @override
  _MyApp createState() => _MyApp();

}

class LoginData {
  String username = "";
  String password = "";
  String name = "";
}



class _MyApp extends State {
  LoginData _loginData = new LoginData();
  GlobalKey<FormState> _formKey = new GlobalKey<FormState>();
  final GlobalKey<ScaffoldState> _scaffoldKey = new GlobalKey<ScaffoldState>();

  void _showMessageInScaffold(String message){
    try {
      _scaffoldKey.currentState.showSnackBar(
          SnackBar(
            content: Text(message),
            action: SnackBarAction(
              label: 'Undo',
              onPressed: () {
        
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
  Widget build(BuildContext inContext) {
    return MaterialApp(home : Scaffold(
        key: _scaffoldKey,
    body : Container(
    padding : EdgeInsets.all(50.0),
    child : Form(

    key : this._formKey,
    child : Column(
    children : [

      TextFormField(
         

          onSaved : (String inValue) {
            this._loginData.name = inValue;
          },
          decoration : InputDecoration(
              hintText : "Name",
              labelText : "Your Name"
          )
      ),

    TextFormField(
    keyboardType :
    TextInputType.emailAddress,
    validator : (String inValue) {
    if (inValue.length == 0) {
    return "Please enter username";
    }
    return null;
    },
        onSaved: (String inValue) {
          this._loginData.username = inValue;
        },
        decoration : InputDecoration(
            hintText : "123@email.com",
            labelText : "Email address"
        )
    ),
      TextFormField(
          obscureText : true,
          validator : (String inValue) {
            if (inValue.length < 5) {
              return "Password must be >=5 in length";
            }
            return null;
          },
          onSaved : (String inValue) {
            this._loginData.password = inValue;
          },
          decoration : InputDecoration(
              hintText : "Password",
              labelText : "Password"
          )
      ),
      RaisedButton(
          child : Text("Log In"),

          onPressed : () {
            Text("${_loginData.name}");

            if (_formKey.currentState.validate()) {
              _formKey.currentState.save();
              _showMessageInScaffold("Welcome to Animate System,Ms.${_loginData.name}, ${_loginData.username}"


              );

              print("Welcome to Animate System , ");
              print("Name: ${_loginData.name}");
              print("Username: ${_loginData.username}");
              print("Password: ${_loginData.password}");

            }
          }
      ) ]




    )))));}}
