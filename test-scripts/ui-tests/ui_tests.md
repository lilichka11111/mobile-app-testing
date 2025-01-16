const { expect } = require('chai');
const { driver } = require('appium');

describe('Login Test', () => {
  it('should login with valid credentials', async () => {
    const usernameField = await driver.$('~username');
    const passwordField = await driver.$('~password');
    const loginButton = await driver.$('~login_button');

    await usernameField.setValue('testuser');
    await passwordField.setValue('password123');
    await loginButton.click();

    const homeScreen = await driver.$('~home_screen');
    expect(homeScreen.isDisplayed()).to.be.true;
  });
});
