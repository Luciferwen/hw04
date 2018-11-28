import tornado.web
import tornado.ioloop
class haowen(tornado.web.RequestHandler):
    def get(self,x):
    
        x=int(x) if x is not None else 9
        html = '''
        <html>
        <body>
        <table>
        '''
        for i in range(1, x+1):
            html +='<TR>'
            for a in range(1, b+1):
                html += '<TD>%d*%d=%d</TD>' % (a,b,b*a)
            html +='</TR>'

        html +='''
        </html>
        </body>
        </table>
        '''
        self.write(html)





        
if __name__ == '__main__':
    app=tornado.web.Application([
        (r"/([0-9])",haowen)
    ]
    )
    app.listen(8888)
    tornado.ioloop.IOLoop.instance().start()
