# Plus Font for React Native

Plus font, packaged for React Native. Exports a typed weight map (PostScript names) that resolves correctly on both iOS and Android — no `Platform.select`, no manual `fontFamily` string guessing.

| | |
|---|---|
| React Native | 0.60+ |
| iOS | ✓ |
| Android | ✓ |

## Install

```bash
npm install @devraj-labs/rn-font-jakaratasans
```

Then add (or update) `react-native.config.js` in your app root to include the font assets:

```js
module.exports = {
  assets: [
    './node_modules/@devraj-labs/rn-font-jakaratasans/assets/fonts',
    // ...other font packages
  ],
};
```

Then link the fonts into your native projects:

```bash
npx react-native-asset
```

Re-run `npx react-native-asset` and rebuild your app whenever you add or update a font package.

## Usage

### With Vajra UI

Register the font in your theme and use it via the `font` prop:

```ts
import { plusFonts } from '@devraj-labs/rn-font-jakaratasans';

createVajraTheme({
  typography: {
    fonts: {
      families: {
        ...plusFonts,
      },
    },
  },
});
```

```tsx
<Text font="plusJakartaSans" fontWeight="200">Sample text</Text>
<Text font="plusJakartaSans" fontWeight="300">Sample text</Text>
```

### Without Vajra UI

The export is a plain object — use it however your app resolves fonts:

```ts
import { plusFonts } from '@devraj-labs/rn-font-jakaratasans';

const styles = StyleSheet.create({
  // plusFonts.plusJakartaSans['200'] → 'PlusJakartaSans-ExtraLight'
  heading: { fontFamily: plusFonts.plusJakartaSans['200'], fontSize: 24 },
  body:    { fontFamily: plusFonts.plusJakartaSans['800'], fontSize: 16 },
});
```

## Font map

| Family | Weight | PostScript name |
|--------|--------|-----------------|
| `plusJakartaSans` | `'200'` | `'PlusJakartaSans-ExtraLight'` |
| `plusJakartaSans` | `'300'` | `'PlusJakartaSans-Light'` |
| `plusJakartaSans` | `'400'` | `'PlusJakartaSans-Regular'` |
| `plusJakartaSans` | `'500'` | `'PlusJakartaSans-Medium'` |
| `plusJakartaSans` | `'600'` | `'PlusJakartaSans-SemiBold'` |
| `plusJakartaSans` | `'700'` | `'PlusJakartaSans-Bold'` |
| `plusJakartaSans` | `'800'` | `'PlusJakartaSans-ExtraBold'` |

## Docs

- [Using a font package](https://github.com/devraj-labs/rn-font-template/blob/main/docs/using-a-package.md) — full usage guide including Vajra UI and standalone examples
- [Creating a font package](https://github.com/devraj-labs/rn-font-template/blob/main/docs/creating-a-package.md) — how this package was built from the template
- [README generation](https://github.com/devraj-labs/rn-font-template/blob/main/docs/readme-generation.md) — how this file is auto-generated

## License

MIT
