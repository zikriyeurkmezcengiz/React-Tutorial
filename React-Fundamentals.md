TODO : Need Format

1.  Composition : Küçük basit fonksiyonları bir araya getirerek daha komple fonksiyonlar bir araya getirmede kullanılır. React component lerinin altyapısında composition vardır. DOT (Does One Thing) i destekler.
2.  Declarative Code : Declarative I anlamak için öncelikle imperative e bakmamız gerekiyor. Klasik bir for döngüsü hayal edelim, bir dizinin elemanları içersinde dönüyoruz ve elemanların her birinin sonuna (‘!’) işareti koyuyoruz. Bunu for döngüsü ile yaptığımızda tüm adımları kendimiz yönetmemiz gerekiyor. Bunun declarative karşılığı ise javascript de map() fonksiyonu. Map fonksiyonunda çoğu adımı bizim yönetmemize gerek yok.


        const people = ['Amanda', 'Farrin', 'Geoff', 'Karen', 'Richard', 'Tyler’]

        ["Amanda!", "Farrin!", "Geoff!", "Karen!", "Richard!", "Tyler!”] (istediğimiz çıktı)

Declarative Code :

        const excitedPeople = people.map(name => name + '!’)

Imperative Code :

        const excitedPeople = []
        for (let i = 0; i < people.length; i++) {
        excitedPeople[i] = people[i] + '!'}

3. Unidirectional Data Flow : React ve Ember gibi diğer script tabanlı dillerde two way data-binding kullanılır. Model içerisinde bir data değiştiğinde view otomatik olarak update olur. Yada user view üzerinde bir değişiklik yaptığında model update olur. Bu ilk bakışta oldukça güçlü bir yöntem gibi gözüksede data nerden değiştiğini ve değişme nedenini her zaman bilmek mümkün değildir.  
   React ise tek yönlü data akısı modelini kullanılır. Bu model de veri akışı her zaman parent conponent den child component e doğrudur. Eğer child component in view in da bir değişiklik yapıldıysa, child bunu parent a iletir ve data değişikliğini model üzerinde parent yapar bu datayı child a gönderir. Böylece her iki taraf da sync olmuş. Bu yapı two way data-bind e göre daha kontrollü yapıdır.

4. React is just a Javascript : React Özünde sadece javascript kodu. Eğer javascript yazarken kendinizi rahat hissediyorsanız. React yazarken de rahat hissedeceksiniz. Meraklanmayın, eğer kendinizi javascript de o kadar da iyi görmüyorsanız, React öğrendikten sonra çok daha iyi hissedersiniz. React size javascript i de öğretecek. Özellikle ES6 özelliklerini kullanarak yazılan bir syntax hakim. Aşağıdaki kod örneğinde, React içerisinde çokça kullanacağımız map() ve filter() fonksiyonlarının kullanımını görebilirsiniz. Map ve filter bir arrow function alarak bir array e uygulanan geriye yine bir array döndüren javascript fonksiyonlarıdır.
   Aşağıdaki kod blogunun yaptıgı iş, musicData veri setini albüm satış sayısı 1000000 dan büyük olacak sekilde filtrelemek ve bu datayı kullanarak “<artist> is a great performer” şeklinde geriye bir araya döndürmek.

const musicData = [
{ artist: 'Adele', name: '25', sales: 1731000 },
{ artist: 'Drake', name: 'Views', sales: 1608000 },
{ artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
{ artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
{ artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
{ artist: 'Original Broadway Cast Recording',
name: 'Hamilton: An American Musical', sales: 820000 },
{ artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
{ artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
{ artist: 'Rihanna', name: 'Anti', sales: 603000 },
{ artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];

const popular = musicData
.filter(music=>music.sales>1000000)
.map(data=> `${data.artist} is a great performer`);

console.log(popular);

4.  createElement() and JSX
    React Dom da element yaratmak için önce React.createElement ile o element i yaratmak daha sonrada o elementi belirli bir node da render etmek gerekiyor. Örnek kullanım aşağıdaki gibi. JSX ise javascript kodu içerisinde html elementlerini kullanmaya olanak sağlar. JSX formatta bir kod yazıp browser üzerinden source u görüntülerseniz, oluşturulan element in yine React.createElement() ile oluşturulduğunu görürsünüz. Bu nedenle React.createElement() i anlamak son derece önemlidir.

React.createElement():

const element = React.createElement('div',{ className: 'greeting'},
React.createElement(‘h2', null1. Composition : Küçük basit fonksiyonları bir araya getirerek daha komple fonksiyonlar bir araya getirmede kullanılır. React component lerinin altyapısında composition vardır. DOT (Does One Thing) i destekler.

2.  Declarative Code : Declarative I anlamak için öncelikle imperative e bakmamız gerekiyor. Klasik bir for döngüsü hayal edelim, bir dizinin elemanları içersinde dönüyoruz ve elemanların her birinin sonuna (‘!’) işareti koyuyoruz. Bunu for döngüsü ile yaptığımızda tüm adımları kendimiz yönetmemiz gerekiyor. Bunun declarative karşılığı ise javascript de map() fonksiyonu. Map fonksiyonunda çoğu adımı bizim yönetmemize gerek yok.

const people = ['Amanda', 'Farrin', 'Geoff', 'Karen', 'Richard', 'Tyler’]

        ["Amanda!", "Farrin!", "Geoff!", "Karen!", "Richard!", "Tyler!”] (istediğimiz çıktı)

Declarative Code : const excitedPeople = people.map(name => name + '!’)
Imperative Code :
const excitedPeople = []
for (let i = 0; i < people.length; i++) {
excitedPeople[i] = people[i] + '!'}

3. Unidirectional Data Flow : React ve Ember gibi diğer script tabanlı dillerde two way data-binding kullanılır. Model içerisinde bir data değiştiğinde view otomatik olarak update olur. Yada user view üzerinde bir değişiklik yaptığında model update olur. Bu ilk bakışta oldukça güçlü bir yöntem gibi gözüksede data nerden değiştiğini ve değişme nedenini her zaman bilmek mümkün değildir.  
   React ise tek yönlü data akısı modelini kullanılır. Bu model de veri akışı her zaman parent conponent den child component e doğrudur. Eğer child component in view in da bir değişiklik yapıldıysa, child bunu parent a iletir ve data değişikliğini model üzerinde parent yapar bu datayı child a gönderir. Böylece her iki taraf da sync olmuş. Bu yapı two way data-bind e göre daha kontrollü yapıdır.

4. React is just a Javascript : React Özünde sadece javascript kodu. Eğer javascript yazarken kendinizi rahat hissediyorsanız. React yazarken de rahat hissedeceksiniz. Meraklanmayın, eğer kendinizi javascript de o kadar da iyi görmüyorsanız, React öğrendikten sonra çok daha iyi hissedersiniz. React size javascript i de öğretecek. Özellikle ES6 özelliklerini kullanarak yazılan bir syntax hakim. Aşağıdaki kod örneğinde, React içerisinde çokça kullanacağımız map() ve filter() fonksiyonlarının kullanımını görebilirsiniz. Map ve filter bir arrow function alarak bir array e uygulanan geriye yine bir array döndüren javascript fonksiyonlarıdır.
   Aşağıdaki kod blogunun yaptıgı iş, musicData veri setini albüm satış sayısı 1000000 dan büyük olacak sekilde filtrelemek ve bu datayı kullanarak “<artist> is a great performer” şeklinde geriye bir araya döndürmek.

const musicData = [
{ artist: 'Adele', name: '25', sales: 1731000 },
{ artist: 'Drake', name: 'Views', sales: 1608000 },
{ artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
{ artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
{ artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
{ artist: 'Original Broadway Cast Recording',
name: 'Hamilton: An American Musical', sales: 820000 },
{ artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
{ artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
{ artist: 'Rihanna', name: 'Anti', sales: 603000 },
{ artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];

const popular = musicData
.filter(music=>music.sales>1000000)
.map(data=> `${data.artist} is a great performer`);

console.log(popular);

4.  createElement() and JSX
    React Dom da element yaratmak için önce React.createElement ile o element i yaratmak daha sonrada o elementi belirli bir node da render etmek gerekiyor. Örnek kullanım aşağıdaki gibi. JSX ise javascript kodu içerisinde html elementlerini kullanmaya olanak sağlar. JSX formatta bir kod yazıp browser üzerinden source u görüntülerseniz, oluşturulan element in yine React.createElement() ile oluşturulduğunu görürsünüz. Bu nedenle React.createElement() i anlamak son derece önemlidir.

React.createElement():

const element = React.createElement('div',{ className: 'greeting'},
React.createElement(‘h2', null, 'Hello world!')
);

JSX :
const greeting = (

 <div className='greeting'>
 <h2>Hello world!</h2>
 </div>
);

Önemli : React.CreateElement() her zaman geriye tek bir object döndürmek zorundadır. Aksi halde hata verir. Bu nedenle JSX de her zaman geriye tek bir object döndürmelidir. En dışta tüm elemenleri encapsulate eden bir element e ihtiyaç vardır. , 'Hello world!')
);

JSX :
const greeting = (

 <div className='greeting'>
 <h2>Hello world!</h2>
 </div>
);

Önemli : React.CreateElement() her zaman geriye tek bir object döndürmek zorundadır. Aksi halde hata verir. Bu nedenle JSX de her zaman geriye tek bir object döndürmelidir. En dışta tüm elemenleri encapsulate eden bir element e ihtiyaç vardır.
