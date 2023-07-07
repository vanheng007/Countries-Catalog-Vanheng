
# Countries Around The World

This project will show a list of countries around the world. The project is purely frontend side where the data we get is from https://restcountries.com

## Case Studies

From the API provided, there are technically only 2 API endpoints we can use which are the 
endpoints that give us all the list of all countries and the one that searches by name.

Since the API won't provide partial data load such as limit response, sorting and so on,
we will implement everything on the client side with the full data loaded from the server/API.

### Technical details to be developed
- Searching/filtering
- Client-side pagination
- Client-side sorting/ordering
- Dialog popup

### Pros
- We have all the data and we can have the UI update instantly

### Drawbacks
- Long initial load (since we query all the data to frontend)
- Add a lot more additional work to the client side to implement such as sorting and pagination
- Add more JS which impacts performances

### Personal Opinions
I believe this was done way before at some point. But right now, at least from my experiences,
is that we have the backend handle everything such as filtering, sorting, and pagination for us, and frontend
only display the correct data.


### Implementation Details
- Everything is put in a single App.vue in order to be concise for reviewers.

### Issues Occurs
- Ran into a specific issue that is more of a bug from the library. It's when using "useOffsetPagination", the problem was that the composable/hook doesn't have async/await to wait for the data total count data to be queried, hence it will always show "Infinity" but I managed to handle that with a custom watch function to change the pageCount when the data loaded from API.

### Libraries/Technologies Involved
- [ESLint](https://eslint.org)
- [Tailwind](https://tailwindcss.com)
- [Headless UI](https://headlessui.com)
- [Lodash](https://lodash.com)
- [VueUse](https://vueuse.org)

### API Reference

Base API Url: https://restcountries.com/v3.1

#### Get all items

```
  GET /all
```

#### Get country by native name or partial name

```
  GET /name/${countryName}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `countryName`| `string` | **Required**. native name or partial name of the country to fetch |


### Run Locally

Clone the project

```bash
  git clone https://github.com/vanheng007/Countries-Catalog-Vanheng.git
```

Go to the project directory

```bash
  cd Countries-Catalog-Vanheng
```

Install dependencies

```bash
  yarn install
```

Start the server

```bash
  yarn dev
```


## Author

> Lyvanhengsun
> 
> Contact: vanhengsunly5555@gmail.com 
> 
> Website: https://www.vanhengsun.com
