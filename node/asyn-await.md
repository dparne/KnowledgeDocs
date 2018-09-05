Reference https://stackoverflow.com/questions/37576685/using-async-await-with-a-foreach-loop

```js
export const uploadFolder = async (nsConfig, folderPath, location = '/') => {
  try {
    const files = await readDir(folderPath);
    for (const fileName of files) {
      let stat = await fsStat(`${folderPath}/${fileName}`);
      if (stat.isDirectory()) {
        let result = await mkDir(nsConfig, `${location}${fileName}`);
        console.log(result);
        let uploadResult = await uploadFolder(nsConfig, `${folderPath}/${fileName}`, `${location}${fileName}/`);
        console.log(uploadResult);
      } else {
        const localFile = `${folderPath}/${fileName}`;
        const destination = `${location}${fileName}`;
        let result = await uploadFile(nsConfig, localFile, destination);
        console.log(result);
      }
    }
    return Promise.resolve(`Upload folder ${folderPath} at ${location} success!`);
  } catch (error) {
    return Promise.reject(error);
  }
};
```

For each was not working so this works... it does it sequentially

Referenced stackoverlow suggest 

```js
async function printFiles () {
  const files = await getFilePaths();

  await Promise.all(files.map(async (file) => {
    const contents = await fs.readFile(file, 'utf8')
    console.log(contents)
  }));
}
```
if I wanna do it parallel which I have not done
