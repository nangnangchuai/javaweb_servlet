
public class GetCookieServlet extends HttpServlet {

	protected void doGet(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		//获得客户端携带的cookie的数据，cookie是放在请求头中从客户端发送到服务器端的
		//取得请求头request中的cookies信息
		Cookie[] cookies = request.getCookies();
		
		//Cookie cookie = new Cookie("name","zhangsan");客户端做了一个name=zhangsan的cookie
		
		//通过cookie名称获得想要的cookie
		if(cookies!=null){
		        //遍历cookies
			for(Cookie cookie : cookies){
				//获得cookie的名称,使用getName()方法
				String cookieName = cookie.getName();
				
				if(cookieName.equals("name")){
					//获得该cookie的值
					String cookieValue = cookie.getValue();
					System.out.println(cookieValue);
				}
			}
		}
