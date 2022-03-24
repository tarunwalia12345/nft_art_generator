nft art generator project made with javascript and canvas api and nodejs

Before you use the nft art generator project, make sure you have node.js and yarn installed.
Installation 🛠️

If you are cloning the project then run this first, otherwise you can download the source code on the release page and skip this step.

git clone https://github.com/tarunwalia12345/nft-art-generator-project

Go to the root of your folder and run this command if you have yarn installed.

yarn install

Alternatively you can run this command if you have node installed.

npm install // I prefer NPM over Yarn

Usage ℹ️

Create your different layers as folders in the 'layers' directory, and add all the layer assets in these directories. You can name the assets anything as long as it has a rarity weight attached in the file name like so: example element#70.png. You can optionally change the delimiter # to anything you would like to use in the variable rarityDelimiter in the src/config.js file.

Once you have all your layers, go into src/config.js and update the layerConfigurations objects layersOrder array to be your layer folders name in order of the back layer to the front layer.

const layerConfigurations = [
  // White BG
  {
    growEditionSizeTo: 34,
    layersOrder: [
      { name: "background_white" },
      { name: "face" }
    ],
  },
  {
    growEditionSizeTo: 43, // 9
    layersOrder: [
      { name: "background_white" },
      { name: "face" },
      { name: "lady_hat" }
    ],
  },
  {
    growEditionSizeTo: 48, // 5
    layersOrder: [
      { name: "background_white" },
      { name: "face" },
      { name: "glasses" }
    ],
  },
  {
    growEditionSizeTo: 49, // 1
    layersOrder: [
      { name: "background_white" },
      { name: "face" },
      { name: "top_hat" }
    ],
  },
  // Red BG
  {
    growEditionSizeTo: 68, // 19
    layersOrder: [
      { name: "background_red" },
      { name: "face" }
    ],
  },
  {
    growEditionSizeTo: 73, // 5
    layersOrder: [
      { name: "background_red" },
      { name: "face" },
      { name: "lady_hat" }
    ],
  },
  {
    growEditionSizeTo: 75, // 2
    layersOrder: [
      { name: "background_red" },
      { name: "face" },
      { name: "glasses" }
    ],
  },
  {
    growEditionSizeTo: 76, // 1
    layersOrder: [
      { name: "background_red" },
      { name: "face" },
      { name: "top_hat" }
    ],
  },
  // Green BG
  {
    growEditionSizeTo: 95, // 19
    layersOrder: [
      { name: "background_green" },
      { name: "face" }
    ],
  },
  {
    growEditionSizeTo: 100, // 5
    layersOrder: [
      { name: "background_green" },
      { name: "face" },
      { name: "lady_hat" }
    ],
  },
  {
    growEditionSizeTo: 102, // 2
    layersOrder: [
      { name: "background_green" },
      { name: "face" },
      { name: "glasses" }
    ],
  },
  {
    growEditionSizeTo: 103, // 1
    layersOrder: [
      { name: "background_green" },
      { name: "face" },
      { name: "top_hat" }
    ],
  },
  // Blue BG
  {
    growEditionSizeTo: 122, // 19
    layersOrder: [
      { name: "background_blue" },
      { name: "face" }
    ],
  },
  {
    growEditionSizeTo: 127, // 5
    layersOrder: [
      { name: "background_blue" },
      { name: "face" },
      { name: "lady_hat" }
    ],
  },
  {
    growEditionSizeTo: 129, // 2
    layersOrder: [
      { name: "background_blue" },
      { name: "face" },
      { name: "glasses" }
    ],
  },
  {
    growEditionSizeTo: 130, // 1
    layersOrder: [
      { name: "background_blue" },
      { name: "face" },
      { name: "top_hat" }
    ],
  },
  // Rainbow BG
  {
    growEditionSizeTo: 131, // 9
    layersOrder: [
      { name: "background_rainbow" },
      { name: "face" }
    ],
  },
  {
    growEditionSizeTo: 135, // 4
    layersOrder: [
      { name: "background_rainbow" },
      { name: "face" },
      { name: "lady_hat" }
    ],
  },
  {
    growEditionSizeTo: 137, // 2
    layersOrder: [
      { name: "background_rainbow" },
      { name: "face" },
      { name: "glasses" }
    ],
  },
  {
    growEditionSizeTo: 138, // 1
    layersOrder: [
      { name: "background_rainbow" },
      { name: "face" },
      { name: "top_hat" }
    ],
  },
];


The name of each layer object represents the name of the folder (in /layers/) that the images reside in.

Optionally you can now add multiple different layerConfigurations to your collection. Each configuration can be unique and have different layer orders, use the same layers or introduce new ones. This gives the artist flexibility when it comes to fine tuning their collections to their needs.

Here is a list of the different blending modes that you can optionally use.

const MODE = {
  sourceOver: "source-over",
  sourceIn: "source-in",
  sourceOut: "source-out",
  sourceAtop: "source-out",
  destinationOver: "destination-over",
  destinationIn: "destination-in",
  destinationOut: "destination-out",
  destinationAtop: "destination-atop",
  lighter: "lighter",
  copy: "copy",
  xor: "xor",
  multiply: "multiply",
  screen: "screen",
  overlay: "overlay",
  darken: "darken",
  lighten: "lighten",
  colorDodge: "color-dodge",
  colorBurn: "color-burn",
  hardLight: "hard-light",
  softLight: "soft-light",
  difference: "difference",
  exclusion: "exclusion",
  hue: "hue",
  saturation: "saturation",
  color: "color",
  luminosity: "luminosity",
};

When you are all ready, run the following command and your outputted art will be in the build/images directory and the json in the build/json directory:

npm run build

or

node index.js
