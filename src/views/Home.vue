<template>
  <div class="home">
    <person 
      v-for="(person, index) in people"
      :key="index"
      v-bind="person"
      :first="index === 0"
      @setActive="handleSetActive" />
  </div>
</template>

<script>
const people = [
  {
    name: 'Dan Laush',
    connections: [
      'Louise Vangundy',
      'Maud Longerbeam',
      'Nick Levell',
      'Bette Treiber',
      'Ying Canney',
      'Osvaldo Nugent',
      'Song Shinkle',
      'Karyn Kistner',
      'Joselyn Hargreaves',
      'Lynette Newsom',
      'Jospeh Ansell'
    ]
  },
  {
    name: 'Toshiko Dutil',
    connections: [
      'Jordan Trembath',
      'Claudette Kolar',
      'Alona Fritch',
      'Marline Lucke',
      'Patti Wilcoxen',
      'Arlette Carroway'
    ]
  },
  {
    name: 'Jordan Trembath',
    connections: [
      'Claudette Kolar',
      'Alona Fritch',
      'Marline Lucke',
      'Patti Wilcoxen',
      'Arlette Carroway',
      'Louise Vangundy'
    ]
  },
  {
    name: 'Claudette Kolar',
    connections: [
      'Alona Fritch',
      'Marline Lucke',
      'Patti Wilcoxen',
      'Arlette Carroway',
      'Louise Vangundy',
      'Becky Duer'
    ]
  },
  {
    name: 'Alona Fritch',
    connections: [
      'Marline Lucke',
      'Patti Wilcoxen',
      'Arlette Carroway',
      'Louise Vangundy',
      'Becky Duer',
      'Madie Cassity'
    ]
  },
  {
    name: 'Marline Lucke',
    connections: [
      'Patti Wilcoxen',
      'Arlette Carroway',
      'Louise Vangundy',
      'Becky Duer',
      'Madie Cassity',
      'Analisa Payan'
    ]
  },
  {
    name: 'Patti Wilcoxen',
    connections: [
      'Arlette Carroway',
      'Louise Vangundy',
      'Becky Duer',
      'Madie Cassity',
      'Analisa Payan',
      'Milly Sund'
    ]
  },
  {
    name: 'Arlette Carroway',
    connections: [
      'Louise Vangundy',
      'Becky Duer',
      'Madie Cassity',
      'Analisa Payan',
      'Milly Sund',
      'Cuc Lederman'
    ]
  },
  {
    name: 'Louise Vangundy',
    connections: [
      'Becky Duer',
      'Madie Cassity',
      'Analisa Payan',
      'Milly Sund',
      'Cuc Lederman',
      'Maud Longerbeam'
    ]
  },
  {
    name: 'Becky Duer',
    connections: [
      'Madie Cassity',
      'Analisa Payan',
      'Milly Sund',
      'Cuc Lederman',
      'Maud Longerbeam',
      'Hipolito Stampley'
    ]
  },
  {
    name: 'Madie Cassity',
    connections: [
      'Analisa Payan',
      'Milly Sund',
      'Cuc Lederman',
      'Maud Longerbeam',
      'Hipolito Stampley',
      'Margarite Weckerly'
    ]
  },
  {
    name: 'Analisa Payan',
    connections: [
      'Milly Sund',
      'Cuc Lederman',
      'Maud Longerbeam',
      'Hipolito Stampley',
      'Margarite Weckerly',
      'Claude Nunn'
    ]
  },
  {
    name: 'Milly Sund',
    connections: [
      'Cuc Lederman',
      'Maud Longerbeam',
      'Hipolito Stampley',
      'Margarite Weckerly',
      'Claude Nunn',
      'Neely Dacruz'
    ]
  },
  {
    name: 'Cuc Lederman',
    connections: [
      'Maud Longerbeam',
      'Hipolito Stampley',
      'Margarite Weckerly',
      'Claude Nunn',
      'Neely Dacruz',
      'Marita Stanberry'
    ]
  },
  {
    name: 'Maud Longerbeam',
    connections: [
      'Hipolito Stampley',
      'Margarite Weckerly',
      'Claude Nunn',
      'Neely Dacruz',
      'Marita Stanberry',
      'Nick Levell'
    ]
  },
  {
    name: 'Hipolito Stampley',
    connections: [
      'Margarite Weckerly',
      'Claude Nunn',
      'Neely Dacruz',
      'Marita Stanberry',
      'Nick Levell',
      'Bette Treiber'
    ]
  },
  {
    name: 'Margarite Weckerly',
    connections: [
      'Claude Nunn',
      'Neely Dacruz',
      'Marita Stanberry',
      'Nick Levell',
      'Bette Treiber',
      'France Aldaco'
    ]
  },
  {
    name: 'Claude Nunn',
    connections: [
      'Neely Dacruz',
      'Marita Stanberry',
      'Nick Levell',
      'Bette Treiber',
      'France Aldaco',
      'Florencio Eddins'
    ]
  },
  {
    name: 'Neely Dacruz',
    connections: [
      'Marita Stanberry',
      'Nick Levell',
      'Bette Treiber',
      'France Aldaco',
      'Florencio Eddins',
      'Bruce Smelcer'
    ]
  },
  {
    name: 'Marita Stanberry',
    connections: [
      'Nick Levell',
      'Bette Treiber',
      'France Aldaco',
      'Florencio Eddins',
      'Bruce Smelcer',
      'Romeo Mabe'
    ]
  },
  {
    name: 'Nick Levell',
    connections: [
      'Bette Treiber',
      'France Aldaco',
      'Florencio Eddins',
      'Bruce Smelcer',
      'Romeo Mabe',
      'Reanna Hanselman'
    ]
  },
  {
    name: 'Bette Treiber',
    connections: [
      'France Aldaco',
      'Florencio Eddins',
      'Bruce Smelcer',
      'Romeo Mabe',
      'Reanna Hanselman',
      'Malvina Carillo'
    ]
  },
  {
    name: 'France Aldaco',
    connections: [
      'Florencio Eddins',
      'Bruce Smelcer',
      'Romeo Mabe',
      'Reanna Hanselman',
      'Malvina Carillo',
      'Valentin Brouse'
    ]
  },
  {
    name: 'Florencio Eddins',
    connections: [
      'Bruce Smelcer',
      'Romeo Mabe',
      'Reanna Hanselman',
      'Malvina Carillo',
      'Valentin Brouse',
      'Hisako Lubinsky'
    ]
  },
  {
    name: 'Bruce Smelcer',
    connections: [
      'Romeo Mabe',
      'Reanna Hanselman',
      'Malvina Carillo',
      'Valentin Brouse',
      'Hisako Lubinsky',
      'Maryrose Hoyle'
    ]
  },
  {
    name: 'Romeo Mabe',
    connections: [
      'Reanna Hanselman',
      'Malvina Carillo',
      'Valentin Brouse',
      'Hisako Lubinsky',
      'Maryrose Hoyle',
      'Vicki Alfrey'
    ]
  },
  { name: 'Reanna Hanselman', connections: [] },
  { name: 'Malvina Carillo', connections: [] },
  { name: 'Valentin Brouse', connections: [] },
  { name: 'Hisako Lubinsky', connections: [] },
  { name: 'Maryrose Hoyle', connections: [] },
  { name: 'Vicki Alfrey', connections: [] },
  { name: 'Angelita Yang', connections: [] },
  { name: 'Michiko Behringer', connections: [] },
  { name: 'Lola Pocock', connections: [] },
  { name: 'Dannette Eichelberger', connections: [] },
  { name: 'Sherlyn Lindblom', connections: [] },
  { name: 'Samara Cope', connections: [] },
  { name: 'Martina Lanz', connections: [] },
  { name: 'Maribeth Moscato', connections: [] },
  { name: 'Twila Balboa', connections: [] },
  { name: 'Hugh Patout', connections: [] },
  { name: 'Tanika Simmerman', connections: [] },
  { name: 'Ying Canney', connections: [] },
  { name: 'Osvaldo Nugent', connections: [] },
  { name: 'Song Shinkle', connections: [] },
  { name: 'Karyn Kistner', connections: [] },
  { name: 'Joselyn Hargreaves', connections: [] },
  { name: 'Lynette Newsom', connections: [] },
  { name: 'Jospeh Ansell', connections: [] }
]

// 'Ying Canney', 'Osvaldo Nugent', 'Song Shinkle', 'Karyn Kistner', 'Joselyn Hargreaves', 'Lynette Newsom', 'Jospeh Ansell'

import Person from '../components/Person'

// via https://stackoverflow.com/a/2450976
const shuffle = array => {
  var currentIndex = array.length,
    temporaryValue,
    randomIndex

  // While there remain elements to shuffle...
  while (0 !== currentIndex) {
    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex)
    currentIndex -= 1

    // And swap it with the current element.
    temporaryValue = array[currentIndex]
    array[currentIndex] = array[randomIndex]
    array[randomIndex] = temporaryValue
  }

  return array
}

export default {
  name: 'home',
  data() {
    return {
      people: shuffle(people).map(person => {
        return {
          ...person,
          active: false,
          connected: false
        }
      })
    }
  },
  methods: {
    handleSetActive(person) {
      console.log('person', person)
      this.updateNames(person)
    },
    updateNames(activePerson) {
      this.people = this.people.map(person => {
        return {
          ...person,
          active: person.name == activePerson.name,
          connected: activePerson.connections.indexOf(person.name) > 0
        }
      })
    }
  },
  components: {
    Person
  }
}
</script>

<style lang='scss' scoped>
.home {
  width: 800px;
  font-size: 32px;
}
</style>
