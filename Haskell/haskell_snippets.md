## Haskell

### Hello World
```haskell
main :: IO ()
main = putStrLn "Hello, World!"
```

### Variables
```haskell
let variable = "Value"
```

### Function definition
```haskell
add :: Int -> Int -> Int
add x y = x + y
```

### Function application
```haskell
result = add 3 5
```

### Lists
```haskell
let myList = [1, 2, 3]
```

### Tuples
```haskell
let myTuple = (1, "Hello")
```

### Patter Matching
```haskell
myFunction :: Int -> String
myFunction 0 = "Zero"
myFunction _ = "Non-zero"
```

### Guards
```haskell
isEven :: Int -> Bool
isEven x
    | x `mod` 2 == 0 = True
    | otherwise      = False
```

### Higher Order Functions
```haskell
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)
```

### Lambda Functions
```haskell
addOne = \x -> x + 1
```

### List comprehension
```haskell
evenNumbers = [x | x <- [1..10], x `mod` 2 == 0]
```

### Type aliases
```haskell
type Name = String
```

### Algebraic data types
```haskell
data Shape = Circle Float | Rectangle Float Float
```

### Record syntax
```haskell
data Person = Person { name :: String, age :: Int }
```

### Recursive functions
```haskell
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)
```

### Monads and IO
```haskell
main :: IO ()
main = do
    putStrLn "Enter your name: "
    name <- getLine
    putStrLn $ "Hello, " ++ name ++ "!"
```

### Fmap (Functor)
```haskell
fmap (+ 1) [1, 2, 3] -- Applies the function to each element
```

### Applicative style
```haskell
(+) <$> [1, 2] <*> [3, 4] -- Applies functions to all combinations
```

### Monads (maybe)
```haskell
safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide x y = Just (x / y)
```

### Monads (either)
```haskell
data MyError = DivideByZero | NegativeResult

safeDivide :: Double -> Double -> Either MyError Double
safeDivide _ 0 = Left DivideByZero
safeDivide x y
    | result < 0 = Left NegativeResult
    | otherwise  = Right result
    where result = x / y
```

### Monads (state)
```haskell
import Control.Monad.State

type MyState = State Int

incrementState :: MyState ()
incrementState = modify (+1)

getStateValue :: MyState Int
getStateValue = get

runMyState :: MyState a -> a
runMyState action = evalState action 0
```

### Error handling with maybe
```haskell
safeHead :: [a] -> Maybe a
safeHead [] = Nothing
safeHead (x:_) = Just x
```

### Error handling with either
```haskell
divide :: Double -> Double -> Either String Double
divide _ 0 = Left "Division by zero"
divide x y = Right (x / y)
```

### Monadic error handling
```haskell
divideMonad :: Double -> Double -> Either String Double
divideMonad x y = do
    if y == 0 then
        Left "Division by zero"
    else
        Right (x / y)
```

### Monadic error handling with maybe
```haskell
safeDivideMonad :: Double -> Double -> Maybe Double
safeDivideMonad x y = do
    guard (y /= 0)
    return (x / y)
```

### Monadic error handling with Either
```haskell
safeDivideMonad :: Double -> Double -> Either String Double
safeDivideMonad x y = do
    if y == 0 then
        Left "Division by zero"
    else
        Right (x / y)
```

### Custom Monadic error handling
```haskell
data MyError = MyError String

instance Show MyError where
    show (MyError msg) = "Custom Error: " ++ msg

instance MonadError MyError (Either MyError) where
    throwError = Left . MyError
    catchError (Right x) _ = Right x
    catchError (Left e) handler = handler e

safeDivideMonad :: Double -> Double -> Either MyError Double
safeDivideMonad x y =
    if y == 0 then
        throwError (MyError "Division by zero")
    else
        return (x / y)

result = safeDivideMonad 10 0 `catchError` (\e -> Left (MyError ("Handled: " ++ show e)))
```

### Monadic Input/Output (with text.IO)
```haskell
import System.IO

main :: IO ()
main = do
    putStr "Enter your name: "
    hFlush stdout
    name <- getLine
    putStrLn $ "Hello, " ++ name ++ "!"
```

### Lazy evaluation
```haskell
fib :: Integer -> Integer
fib n = fibs !! fromIntegral n
    where fibs = 0 : 1 : zipWith (+) fibs (tail fibs)
```

### Memoization
```haskell
fib :: Integer -> Integer
fib = (map fib' [0..] !!)
    where fib' 0 = 0
          fib' 1 = 1
          fib' n = fib (n-1) + fib (n-2)
```

### Monadic parsing with Parsec
```haskell
import Text.Parsec
import Text.Parsec.String

parser :: Parser Int
parser = do
    x <- many1 digit
    if length x > 2
        then fail "Number too large"
        else return (read x)

parseResult = parse parser "" "123"
```

### Reading and writing files
```haskell
import System.IO

main :: IO ()
main = do
    writeFile "output.txt" "Hello, Haskell!"
    contents <- readFile "output.txt"
    putStrLn contents
```

### Working with Monads
```haskell
import Control.Monad

printList :: [Int] -> IO ()
printList xs = forM_ xs print
```

### Using Data.Map for key-value pairs
```haskell
import qualified Data.Map as Map

myMap = Map.fromList [("key1", "value1"), ("key2", "value2")]
```

### Using data.set for sets
```haskell
import qualified Data.Set as Set

mySet = Set.fromList [1, 2, 3, 3]
```

### Sorting lists
```haskell
import Data.List

sortedList = sort [3, 1, 2]
```

### Zipping Lists
```haskell
list1 = [1, 2, 3]
list2 = ["one", "two", "three"]
zippedList = zip list1 list2
```

### Using data.text for text processing
```haskell
import qualified Data.Text as T

text1 = T.pack "Hello, "
text2 = T.pack "Haskell!"
combinedText = T.append text1 text2
```

### Working with data.byteString for binary data
```haskell
import qualified Data.ByteString as BS

byteString = BS.pack [72, 101, 108, 108, 111]  -- "Hello"
```

### Concurrent programming (Control.Concurrent)
```haskell
import Control.Concurrent

main :: IO ()
main = do
    tid <- forkIO $ putStrLn "Hello from another thread"
    putStrLn "Hello from the main thread"
    threadDelay 2000000
```

### Working with JSON (aeson library)
```haskell
{-# LANGUAGE DeriveGeneric #-}

import Data.Aeson
import GHC.Generics

data Person = Person
    { name :: String
    , age :: Int
    } deriving (Generic, Show)

instance FromJSON Person
instance ToJSON Person

main :: IO ()
main = do
    let jsonString = "{\"name\":\"Alice\",\"age\":30}"
    case decode jsonString of
        Just person -> print (person :: Person)
        Nothing     -> putStrLn "Invalid JSON"
```

### Parsing XML (xml-conduit library)
```haskell
{-# LANGUAGE OverloadedStrings #-}

import Text.XML
import Text.XML.Cursor

main :: IO ()
main = do
    let doc = parseText_ def "<root><item>1</item><item>2</item></root>"
    let cursor = fromDocument doc
    let values = cursor $// element "item" >=> attribute "value"
    print values
```

### Using ST monads for mutable data
```haskell
import Control.Monad.ST
import Data.STRef

main :: IO ()
main = do
    let result = runST $ do
        ref <- newSTRef 0
        writeSTRef ref 42
        readSTRef ref
    print result
```

### Using Data.Vetor for efficient sequences
```haskell
import qualified Data.Vector as V

main :: IO ()
main = do
    let vector = V.fromList [1..1000000] :: V.Vector Int
    let sum = V.foldl' (+) 0 vector
    print sum
```

### Using STM for concurrent programmnig
```haskell
import Control.Concurrent.STM

main :: IO ()
main = do
    account <- atomically $ newTVar 1000
    forkIO $ withdraw account 500
    forkIO $ deposit account 300
    threadDelay 2000000
    balance <- atomically $ readTVar account
    print balance

withdraw :: TVar Int -> Int -> IO ()
withdraw account amount = atomically $ do
    balance <- readTVar account
    writeTVar account (balance - amount)

deposit :: TVar Int -> Int -> IO ()
deposit account amount = atomically $ do
    balance <- readTVar account
    writeTVar account (balance + amount)
```

### Custom monads with mtl library
```haskell
{-# LANGUAGE FlexibleContexts #-}

import Control.Monad.Reader

data AppConfig = AppConfig { appName :: String }

sayHello :: Reader AppConfig String
sayHello = do
    app <- ask
    return $ "Hello, " ++ appName app

main :: IO ()
main = do
    let config = AppConfig { appName = "Haskell" }
    let result = runReader sayHello config
    putStrLn result
```

### Creating a RESTful API server (with Servant library)
```haskell
{-# LANGUAGE DataKinds #-}
{-# LANGUAGE TypeOperators #-}

import Data.Proxy
import Network.Wai
import Network.Wai.Handler.Warp
import Servant

type API = "hello" :> Get '[JSON] String

server :: Server API
server = return "Hello, Haskell!"

api :: Proxy API
api = Proxy

app :: Application
app = serve api server

main :: IO ()
main = run 8080 app
```

### Using template haskell with TH library
```haskell
{-# LANGUAGE TemplateHaskell #-}

import Language.Haskell.TH

greet :: String -> Q [Dec]
greet name = do
    let funName = mkName "sayHello"
    let body = NormalB (AppE (LitE (StringL "Hello, ")) (VarE (mkName name)))
    return [FunD funName [Clause [] body []]]

greet "Alice"

main :: IO ()
main = putStrLn $(sayHello "Alice")
```

### Using Data.ByteString.Lazy for efficient binary data
```haskell
import qualified Data.ByteString.Lazy as BSL

byteString = BSL.pack [72, 101, 108, 108, 111]  -- "Hello"
```

### Parsing CSV with cassava library
```haskell
import qualified Data.Csv as Csv
import Data.Vector (Vector)

data Person = Person
    { name :: String
    , age :: Int
    } deriving (Show)

instance Csv.FromNamedRecord Person where
    parseNamedRecord r = Person <$> r Csv..: "name" <*> r Csv..: "age"

main :: IO ()
main = do
    let csvData = "name,age\nAlice,30\nBob,25\n"
    case Csv.decodeByName csvData of
        Left err -> putStrLn err
        Right (_, v) -> print (v :: Vector Person)
```

### Working with type classes with typeclassopedia
```haskell
class MyShow a where
    myShow :: a -> String

instance MyShow Int where
    myShow = show

instance MyShow Bool where
    myShow True = "Yes"
    myShow False = "No"

main :: IO ()
main = do
    print (myShow (5 :: Int))
    print (myShow True)
```

### Using data.text.lazy for text processing
```haskell
import qualified Data.Text.Lazy as TL

text1 = TL.pack "Hello, "
text2 = TL.pack "Haskell!"
combinedText = TL.append text1 text2
```

### Building a RESTful API client with http-client library
```haskell
import Network.HTTP.Client
import Network.HTTP.Client.TLS

main :: IO ()
main = do
    manager <- newManager tlsManagerSettings
    request <- parseRequest "https://api.example.com/resource"
    response <- httpLbs request manager
    putStrLn $ "Response status code: " ++ show (responseStatus response)
```

### Using data.text.encoding for text encoding/decoding
```haskell
import qualified Data.Text as T
import qualified Data.Text.Encoding as TE

encodedText = TE.encodeUtf8 (T.pack "Hello, Haskell!")
decodedText = T.unpack (TE.decodeUtf8 encodedText)
```

### Concurrency with softwaare transactional memory (STM)
```haskell
import Control.Concurrent.STM

main :: IO ()
main = do
    account <- atomically $ newTVar 1000
    forkIO $ withdraw account 500
    forkIO $ deposit account 300
    threadDelay 2000000
    balance <- atomically $ readTVar account
    print balance

withdraw :: TVar Int -> Int -> IO ()
withdraw account amount = atomically $ do
    balance <- readTVar account
    writeTVar account (balance - amount)

deposit :: TVar Int -> Int -> IO ()
deposit account amount = atomically $ do
    balance <- readTVar account
    writeTVar account (balance + amount)
```

### Concurrency with parallelism
```haskell
import Control.Parallel

main :: IO ()
main = do
    let x = 2 + 3
    let y = 4 + 5
    let result = x `par` y `pseq` (x + y)
    print result
```

### Building a GraphQL API server with graphql-api library
```haskell
{-# LANGUAGE DeriveGeneric #-}
{-# LANGUAGE OverloadedStrings #-}

import Data.Aeson
import GHC.Generics
import Web.Scotty
import Web.Scotty.Internal.Types (ActionT)

data Person = Person
    { name :: String
    , age :: Int
    } deriving (Generic)

instance ToJSON Person

main :: IO ()
main = scotty 3000 $ do
    post "/graphql" $ do
        -- Parse GraphQL query and execute
        json (Person "Alice" 30)
```

### Using mtl for monad transformers
```haskell
{-# LANGUAGE FlexibleContexts #-}

import Control.Monad.Reader
import Control.Monad.Except

data AppConfig = AppConfig { appName :: String }
data AppError = MyError String

type MyApp a = ReaderT AppConfig (ExceptT AppError IO) a

sayHello :: String -> MyApp String
sayHello name = do
    app <- ask
    if appName app /= "Haskell"
        then throwError (MyError "Invalid app name")
        else return $ "Hello, " ++ name

main :: IO ()
main = do
    let config = AppConfig { appName = "Haskell" }
    result <- runExceptT (runReaderT (sayHello "Alice") config)
    case result of
        Left (MyError err) -> putStrLn err
        Right msg -> putStrLn msg
```




