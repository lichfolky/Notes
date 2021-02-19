### the TRY util
import scala.util.{Try, Success, Failure}

> def makeInt(s: String): Int = Try(s.toInt) > match {  
>      case Success(n) => n  
>      case Failure(_) => 0  
>       }
