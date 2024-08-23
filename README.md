
// Import Web3 library
const Web3 = require('web3');

// Set up Web3 provider (e.g., MetaMask, Infura)
const provider = new Web3.providers.HttpProvider('(link unavailable)');

// Get the deployed smart contract address and ABI
const contractAddress = '0x...';
const contractABI = [...];

// Create a new Web3 contract instance
const calculatorContract = new Web3.eth.Contract(contractABI, contractAddress);

// Define a function to perform calculations
async function calculate(operation, num1, num2) {
  try {
    const result = await calculatorContract.methods[operation](num1, num2).call();
    return result;
  } catch (error) {
    console.error(error);
  }
}

// Use the calculate function to perform calculations
document.getElementById('add').addEventListener('click', () => {
  const num1 = parseInt(document.getElementById('num1').value);
  const num2 = parseInt(document.getElementById('num2').value);
  calculate('add', num1, num2).then(result => {
    document.getElementById('result').innerHTML = result;
  });
});

document.getElementById('sub').addEventListener('click', () => {
  const num1 = parseInt(document.getElementById('num1').value);
  const num2 = parseInt(document.getElementById('num2').value);
  calculate('sub', num1, num2).then(result => {
    document.getElementById('result').innerHTML = result;
  });
});

document.getElementById('mul').addEventListener('click', () => {
  const num1 = parseInt(document.getElementById('num1').value);
  const num2 = parseInt(document.getElementById('num2').value);
  calculate('mul', num1, num2).then(result => {
    document.getElementById('result').innerHTML = result;
  });
});

document.getElementById('div').addEventListener('click', () => {
  const num1 = parseInt(document.getElementById('num1').value);
  const num2 = parseInt(document.getElementById('num2').value);
  calculate('div', num1, num2).then(result => {
    document.getElementById('result').innerHTML = result;
  });
});
