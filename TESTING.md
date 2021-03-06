## EmojiCryptor

James Covino, Cody Hegwer, Annie Lydens

## Automated testing setup guide

1. Clone or download repository.

2. Install pytest, 'pip3 install pytest'

3. Go to project folder "teamworldbot/"

4. While in project directory, run tests with 'python3 -m pytest'

5. If you want to modify tests go to directory "teamworldbot/tests/",
    Python file names and functions must start with "test_"


## TEST 1 - LOGIN

#### Use case name
    Verify login with valid user name and password.

##### Description
Ensure users can login to the site for future additional features.

##### Pre-conditions
User has valid login credentials. Login html is deployed.

##### Test steps
    1. Navigate to login page.
    2. Provide valid user name.
    3. Provide valid password.
    4. Click login button.

##### Expected result
User will be logged in and taken to separate html page.

##### Actual result
In development:
  - User is logged in and taken to separate html page.

On production:
  - Results in an Internal Server Error. We need to migrate over to Postgres, as [Heroku does not support SQLite](https://devcenter.heroku.com/articles/sqlite3).

##### Status (Pass/Fail)
Fail

##### Notes
We need to use Postgres instead of SQLite.

##### Post-conditions
User is given Internal Server Error.


## TEST 2 - Encrypt

#### Use case name
    Encrypt a message via deployed app.

#### Description
Be able to encrypt a message through our website. User will have the option for multiplier and key to better encrypt their message.

#### Pre-conditions
User uses valid ASCII digits / letters. Any other character is ignored for encryption purposes.

#### Test steps
    1. Enter message to encrypt in form field.
    2. Press "Encrypt Me!" button.
    3. Receive encrypted message.

#### Expected result
Any valid characters will be encrypted. Other non-valid characters will be concatenated with string but not encrypted.

#### Actual result
Same as expected result.

#### Status (Pass/Fail)
Pass

#### Notes
Multiplier / key fields have not been implemented yet, but actual encryption works.

#### Post-conditions
Current html is altered to show user encrypted message.


## TEST 3 - Decrypt

#### Use case name
    Decrypt a message via deployed app.

#### Description
Be able to decrypt a message through our website. User will have the option for multiplier and key to match the cipher provided from encryption.

#### Pre-conditions
User uses valid ASCII digits / letters. Any other character is ignored for encryption purposes.

#### Test steps
    1. Enter message to decrypt in form field.
    2. Press "Decrypt Me!" button.
    3. Receive decrypted message.

#### Expected result
Any emoji's will be decrypted. Other non-valid characters will remain the same in output.

#### Actual result
Emojis are decrypted. Non-emojis remain the same in output.

#### Status (Pass/Fail)
Pass (kinda)

#### Notes
Multiplier / key fields have not been implemented yet, but actual Decryption works.
Copying Emoji's from slack into Decryption App isn't working. Instead of the Emoji being pasted into the input bar :smile: :rocket: ... is pasted in.  As, a result no decryption occurs and the same message is relayed back.

#### Post-conditions
Current html is altered to show user Decrypted message.
