# DartPad
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatefulWidget {
  MyApp({Key key}) : super(key: key);
  @override
  _MyApp createState() => _MyApp();
}

class LoginData {
  String username = "";
  String name = "";
  String address = "";
  String tel = "";
  String password = "";
}

class _MyApp extends State {
  String _textStringName = '';
  String _textStringAddress = '';
  String _textStringTel = '';
  String _textStringEmail = '';

  LoginData _loginData = new LoginData();
  GlobalKey<FormState> _formKey = new GlobalKey<FormState>();
  @override
  Widget build(BuildContext inContext) {
    return MaterialApp(
        home: Scaffold(
            body: Container(
                padding: EdgeInsets.all(50.0),
                child: Form(
                    key: this._formKey,
                    child: Column(children: [
                      
                       TextFormField(
                          keyboardType: TextInputType.emailAddress,
                          validator: (String inValue) {
                            if (inValue.length == 0) {
                              return "Please enter name and surname";
                            }
                            return null;
                          },
                          onSaved: (String inValue) {
                            this._loginData.name = inValue;
                          },
                          decoration: InputDecoration(
                              hintText: "Name and Surname",
                              labelText: "Name and Surname")),
                      
                      TextFormField(
                          keyboardType: TextInputType.emailAddress,
                          validator: (String inValue) {
                            if (inValue.length == 0) {
                              return "Please enter address";
                            }
                            return null;
                          },
                          onSaved: (String inValue) {
                            this._loginData.address = inValue;
                          },
                          decoration: InputDecoration(
                              hintText: "address",
                              labelText: "Address")), 
                      TextFormField(
                          keyboardType: TextInputType.emailAddress,
                          validator: (String inValue) {
                            if (inValue.length == 0) {
                              return "Please enter phone";
                            }
                            return null;
                          },
                          onSaved: (String inValue) {
                            this._loginData.tel = inValue;
                          },
                          decoration: InputDecoration(
                              hintText: "Tel",
                              labelText: "Tel")),
                      TextFormField(
                          keyboardType: TextInputType.emailAddress,
                          validator: (String inValue) {
                            if (inValue.length == 0) {
                              return "Please enter username";
                            }
                            return null;
                          },
                          onSaved: (String inValue) {
                            this._loginData.username = inValue;
                          },
                          decoration: InputDecoration(
                              hintText: "none@none.com",
                              labelText: "Username (eMail address)")),
                      TextFormField(
                          obscureText: true,
                          validator: (String inValue) {
                            if (inValue.length < 10) {
                              return "Password must be >= 10 in length";
                            }
                            return null;
                          },
                          onSaved: (String inValue) {
                            this._loginData.password = inValue;
                          },
                          decoration: InputDecoration(  
                              hintText: "Password", labelText: "Password")),
                      RaisedButton(
                        child: Text("Log In!"),
                        onPressed: () {
                          if (_formKey.currentState.validate()) {
                            _formKey.currentState.save();
                            print("Username: ${_loginData.username}");
                            print("Password: ${_loginData.password}");
                            _dosomething();
                          }
                        },
                      ),
                      Text(_textStringName),
                      Text(_textStringAddress),
                      Text(_textStringTel),
                      Text(_textStringEmail),
                     
                    ])))));
  }

  void _dosomething() {
    setState(() {
      _textStringName = "WELCOME  ${_loginData.name}";
      _textStringAddress = "Address : ${_loginData.address}";
      _textStringTel = "Tel : ${_loginData.tel}";
      _textStringEmail = "Mail : ${_loginData.username}";
      
      
      
      
    });
  }
}
