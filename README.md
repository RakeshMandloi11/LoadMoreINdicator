# LoadMoreINdicator

    private var activityIndicator: LoadMoreActivityIndicator?
    private func setLoadMoreLoader() {
        activityIndicator = LoadMoreActivityIndicator(scrollView: tableVIew,
                                                      spacingFromLastCell: 10,
                                                      spacingFromLastCellToLoadere: 50)

    }

       // Implement delegate 
    func scrollViewDidScroll(_ scrollView: UIScrollView) {
        activityIndicator?.start {
            DispatchQueue.global(qos: .utility).async {
                 // do your work here 
                DispatchQueue.main.asyncAfter(deadline: .now() + 1.0) {
                    // stop Indicator when done
                    self.activityIndicator?.stop()
                    
                }
              }
        }
    }
