# yargs
Personal achievement for learning and implementing CLI

## Yargs Nedir?

Yargs argumanlari ogelerine ayirarak interaktif command line tools-CLI olusturmamizda yardimci olan ve iyi bir kullanici arayuzu uretmemizi saglayan bie moduldur.

Yargs ile:

- commands(komutlar) ve grouped options(opsiyonlar); "module run -n --force" gibi  
- argumanlari baz alarak dinamik help menusu
- bash tabanli kisayollar
saglanir.

## Yargs Uygulamasi

Yargs modulunu yuklemek icin terminal'den projemizi secip `npm` kullanarak asagidaki komutu yazalim:

```
$ npm install --save yargs
```
Daha sonra ise, **example.js** dosyasi olusturalim ve asagidaki kod blogu ile baslayalim:

```
#!/usr/bin/env node

require('yargs')
  .scriptName("pirate-parser")
  .usage('$0 <cmd> [args]')
  .command('hello [name]', 'welcome ter yargs!', (yargs) => {
    yargs.positional('name', {
      type: 'string',
      default: 'Cambi',
      describe: 'the name to say hello to'
    })
  }, function (argv) {
    console.log('hello', argv.name, 'welcome to yargs!')
  })
  .help()
  .argv

```
Su sekilde bir cikti almamiz gerekiyor:

![alt](yargs_help.png)

Daha sonra ise, hello komutunu calistiralim:

```
$ node example.js hello --name Parrot
```

![alt](parrot.png)
