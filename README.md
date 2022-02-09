# DropDown
Kod Kullanımı


void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: "DropDownMenu",
      home: AnaMenu(),
    );
  }
}

class AnaMenu extends StatefulWidget {
  const AnaMenu({Key? key}) : super(key: key);

  @override
  _AnaMenuState createState() => _AnaMenuState();
}

class _AnaMenuState extends State<AnaMenu> {
  final List<String> itemler = [
    "PN4",
    "PN5",
    "PN6",
    "PN7",
    "PN8",
  ];

  String degerler = "PN4";

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        title: "Menu",
        debugShowCheckedModeBanner: false,
        home: Scaffold(
          body: DropdownButton(
              value: degerler,
              items: itemler.map((String itemlers) {
                return DropdownMenuItem(value: itemlers, child: Text(itemlers));
              }).toList(),
              onChanged: (yenideger) {
                setState(() {
                  degerler = yenideger.toString();
                });
              }),
        ));
